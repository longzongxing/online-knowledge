# [java bean validation 参数验证](https://www.cnblogs.com/xiaogangfan/p/5987659.html)



## 一、前言

　　在后台开发过程中，对参数的校验成为开发环境不可缺少的一个环节。比如参数不能为null，email那么必须符合email的格式，如果手动进行if判断或者写正则表达式判断无意开发效率太慢，在时间、成本、质量的博弈中必然会落后。所以把校验层抽象出来是必然的结果，下面说下几种解决方案。

## 二、几种解决方案

　　1、struts2的valid可以通过配置xml，xml中描述规则和返回的信息，这种方式比较麻烦、开发效率低，不推荐

　　2、validation bean 是基于JSR-303标准开发出来的，使用注解方式实现，及其方便，但是这只是一个接口，没有具体实现.Hibernate Validator是一个hibernate独立的包，可以直接引用，他实现了validation bean同时有做了扩展，比较强大 ，实现图如下：

![img](https://images2015.cnblogs.com/blog/827161/201610/827161-20161022141655263-2092739140.png)

3、[oval](http://oval.sourceforge.net/) 是一个可扩展的Java对象数据验证框架，验证的规则可以通过配置文件、Annotation、POJOs 进行设定。可以使用纯 Java 语言、JavaScript 、Groovy 、BeanShell 等进行规则的编写，本次不过多讲解



## 三、bean validation 框架验证介绍

　　bean validation 包放在maven上维护,最新包的坐标如下：

```
`<``dependency``>``    ``<``groupId``>javax.validation</``groupId``>``    ``<``artifactId``>validation-api</``artifactId``>``    ``<``version``>1.1.0.Final</``version``>``</``dependency``>`
```

　　 [点击这里查看最新的坐标地址](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22javax.validation%22%20AND%20a%3A%22validation-api%22　)

　　 下载之后打开这个包，有个package叫constraints，里面放的就是验证的的注解：

![img](https://images2015.cnblogs.com/blog/827161/201610/827161-20161022150209967-1863141332.png)

```java
package com.shishang;

import javax.validation.constraints.*;
import java.io.Serializable;
import java.math.BigDecimal;
import java.util.Date;

public class Student implements Serializable {


    @NotNull(message = "名字不能为空")
    private String name;

    @Size(min = 6,max = 30,message = "地址应该在6-30字符之间")
    private String address;

    @DecimalMax(value = "100.00",message = "体重有些超标哦")
    @DecimalMin(value = "60.00",message = "多吃点饭吧")
    private BigDecimal weight;

    private String friendName;
    @AssertTrue
    private Boolean isHaveFriend(){
        return friendName != null?true:false;
    }

    @Future(message = "生日必须在当前实践之前")
    private Date birthday;

    @Pattern(regexp = "^(.+)@(.+)$",message = "邮箱的格式不合法")
    private String email;


    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }

    public BigDecimal getWeight() {
        return weight;
    }

    public void setWeight(BigDecimal weight) {
        this.weight = weight;
    }

    public String getFriendName() {
        return friendName;
    }

    public void setFriendName(String friendName) {
        this.friendName = friendName;
    }

    public Date getBirthday() {
        return birthday;
    }

    public void setBirthday(Date birthday) {
        this.birthday = birthday;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }
}
```



4、总结 

-   像@NotNull、@Size等比较简单也易于理解，不多说
-   因为bean validation只提供了接口并未实现，使用时需要加上一个provider的包，例如hibernate-validator
-   @Pattern 因为这个是正则，所以能做的事情比较多，比如中文还是数字、邮箱、长度等等都可以做
-   @AssertTRue 这个与其他的校验注解有着本质的区别，这个注解适用于多个字段。例子中isHaveFriend方法依赖friendName字段校验
-   验证的api是经过我加工了一下，这样可以批量返回校验的信息
-   有时我们需要的注解可能没有提供，这时候就需要自定义注解，写实现类，下面说一下自定义注解的使用

## 四、自定义bean validation 注解验证

　　有时框架自带的没法满足我们的需求，这时就需要自己动手丰衣足食了，恩恩 ，这个不难，下面说下。

　　这个例子验证字符串是大写还是小写约束标注，代码如下:

　　1、**枚举类型CaseMode, 来表示大写或小写模式**

```java
package com.defineconstrain;

/**
 * created by xiaogangfan
 * on 16/10/25.
 */
public enum CaseMode {
    UPPER,
    LOWER;
}
```

2、**定义一个CheckCase的约束标注** 

```java
package com.defineconstrain;

/**
 * created by xiaogangfan
 * on 16/10/25.
 */
import static java.lang.annotation.ElementType.*;
import static java.lang.annotation.RetentionPolicy.*;

import java.lang.annotation.Documented;
import java.lang.annotation.Retention;
import java.lang.annotation.Target;

import javax.validation.Constraint;
import javax.validation.Payload;

@Target( { METHOD, FIELD, ANNOTATION_TYPE })
@Retention(RUNTIME)
@Constraint(validatedBy = CheckCaseValidator.class)
@Documented
public @interface CheckCase {

    String message() default "{com.mycompany.constraints.checkcase}";

    Class<?>[] groups() default {};

    Class<? extends Payload>[] payload() default {};

    CaseMode value();

}
```

　3、**约束条件CheckCase的验证器**

```java
package com.defineconstrain;

/**
 * created by xiaogangfan
 * on 16/10/25.
 */
import javax.validation.ConstraintValidator;
import javax.validation.ConstraintValidatorContext;

public class CheckCaseValidator implements ConstraintValidator<CheckCase, String> {

    private CaseMode caseMode;

    public void initialize(CheckCase constraintAnnotation) {
        this.caseMode = constraintAnnotation.value();
    }

    public boolean isValid(String object, ConstraintValidatorContext constraintContext) {

        if (object == null)
            return true;

        if (caseMode == CaseMode.UPPER)
            return object.equals(object.toUpperCase());
        else
            return object.equals(object.toLowerCase());
    }

}
```

4、在Student.java中增加一个属性

```java
1 @CheckCase(value = CaseMode.LOWER,message = "名字的拼音需要小写")
2     private String spellName;
```

