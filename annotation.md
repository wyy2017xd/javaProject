# spring boot
### @RequestMapping
    解释：用来请求地址的映射，可用于类或方法上。用于类上，表示类的所有响应请求的方法都是以该地址作为父路径。
    
##### 六大属性：
1. value：指定请求的实际地址，指定的地址可以使具体地址，可以是RestFul动态获取，也可以使用正则设置；
2. method：指定的method的类型，分为get,post,put,delete等；
3. consumes:指定处理请求的提交内容类型（conten_type),例如application/json,text/html;
4. produces: 指定返回的内容类型，仅当request请求头中的（Accept）类型中包含指定类型才返回；
5. params：指定request中必须包含某些参数值是，才让该方法处理；
6. headers:指定request中必须包含某些指定的header，才让该方法处理。

### @RestController
1. 作用等同于@Controller+@ResponseBody
2. @Controller，表明控制器类，将@Controller注解的类注入Spring容器中；
3. @RequestMapping注解是用来映射请求的，即指明处理器可以处理哪些URL请求，该注解既可以用在类上，也可以用在方法上。当使用@RequestMapping标记控制器类时，方法的请求地址是相对类的请求地址而言的；当没有使用@RequestMapping标记类时，方法的请求地址是绝对路径。@RequestMapping的地址可以是uri变量，并且通过@PathVariable注解获取作为方法的参数。也可以是通配符来筛选请求地址。
4. @ResponseBody表示方法的返回值直接以指定的格式写入Http response body中，而不是解析为跳转路径。格式的转换是通过HttpMessageConverter中的方法实现的，因为它是一个接口，因此由其实现类完成转换。如果要求方法返回的是json格式数据，而不是跳转页面，可以直接在类上标注@RestController，而不用在每个方法中标注@ResponseBody，简化了开发过程.

### @Autowired
    自动装配，从IOC容器去查找到，并返回给该属性。　其实在启动spring IoC时，容器自动装载了一个AutowiredAnnotationBeanPostProcessor后置处理器，当容器扫描到@Autowied、@Resource或@Inject时，就会在IoC容器自动查找需要的bean，并装配给该对象的属性。

### @PathVariable
带占位符的 URL 是 Spring3.0 新增的功能，该功能在SpringMVC 向 REST 目标挺进发展过程中具有里程碑的意义
通过 @PathVariable 可以将 URL 中占位符参数绑定到控制器处理方法的入参中：URL 中的 {xxx} 占位符可以通过@PathVariable(“xxx“) 绑定到操作方法的入参中。

### @ConfigurationProperties
获取一组相关的配置
