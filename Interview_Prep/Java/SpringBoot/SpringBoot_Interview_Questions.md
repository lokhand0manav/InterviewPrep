## Spring Boot Interview Questions Prep:
### Ref: https://www.youtube.com/watch?v=1vg1Qg6cugc
- ![[Pasted image 20220826110814.png]]
- We can change the port by adding (Overriding) server.port in application.properties ( resided under source/resources)
- ![[Pasted image 20220826214750.png]]
	- The spring-boot-starter-web dependency is responsible for the Tomcat server
	- So as I investigated this further, in the spring-boot-starter-web there is pom in this dependency as well, which has the spring-boot-starter-tomcat dependency, they excluded that using : `<exclusions><exclusion><groupId>.....</groupId><artifactId>....</artifactId><exclusion></exclusions>` <-- here it mentions to exclude the tomcat dependency.
- We can use our own webserver as well. We can avoid using the default webserver or the embedded web server of SpringBoot. ![[Pasted image 20220826225223.png]]
- ![[Pasted image 20220826230034.png]]
- How to use a value from application.property in your java class:
	- use @Value("${server.port}") and annote a variable 
- What is `@RestController`
	- This is combination of `@Controller` and `@ResponseBody`. If we just use @Controller over the top of class, we will have to add @ResponseBody over every method of the controller, or else we will be resulted with an error.
	- This `@ResponseBody` tells the Framework that, it wont require a template to display the data, rather everything will be written on a Response Body.
	- ![[Pasted image 20220826231808.png]]
	- ![[Pasted image 20220826232229.png]]
- ![[Pasted image 20220826232252.png]]
- `@GetMapping` is a specialization of `@RequestMapping`, get mapping can only handle GET request, whil RequestMapping can do all.
- Profiling in springboot could be considered as profiles for various environment
	- For Prod we have diff configs, for dev we have lets say diff configs..
	- Use `spring-profiles-active` in `application.properties`
	- ![[Pasted image 20220826235737.png]]
- ### Ref: https://www.youtube.com/watch?v=9SGDpanrc8U&t=2559s
	- `@Autowiring` means we will be using the Dependency injection in our class. So while fetching the class object avoid `new` and try using @Autowired over your constructor to autowire the object.
		- Also the class whose object is being injected should be annotated as `@Component` or `@Service` both are same but Service is more readable if you are adding it above the class
- ### Ref: https://www.interviewbit.com/blog/spring-boot-architecture/#:~:text=Spring%20Boot%20uses%20a%20hierarchical,above%20it%20(%20hierarchical%20structure).
	- SpringBoot follows a layer architecture or heirarchical architecture.
		1.  Presentation Layer
		2.  Business Layer
		3.  Persistence Layer
		4.  Database Layer
