#pattern #creationalPattern 

**Definition:**
- Create and manage an instance of an abstract interface
- Lifecycle management (create, initialize, ...)
- The Implementation can be injected in a client via
	- Setter injection
	- Constructor injection

```java
public interface Service {
      void call();
}

public class LinuxService implements Service {}
public class MacService implements Service {}
public class WindowsService implements Service {}

public class Client {

      @Autowired
      private Service service;

      public void doSomething() {
            service.call();
      }
}

public class Assembler {

      public static void autowire(Object obj) {
            Class<?> cls = obj.getClass();

            for(Field field : cls.getDeclaredFields())
                  if(field.getType() == Service.class && 
	                  field.isAnnotationPresent(Autowired.class))
							inject(field, obj);          
      }

  

      private static Service getService() {

            String osName = System.getProperty("os.name").toLowerCase();

          Service service;
            if(osName.indexOf("win") >= 0) service = new WindowsService();
            else if(osName.indexOf("mac") >= 0) service = new MacService();
            else if((osName.indexOf("ix") > 0)) service = new LinuxService();
            else
				throw new IllegalArgumentException("Cannot instanitate " + osName);

            return service;
      }

      private static void inject(Field field, Object obj) {

            Service service = getService();
            try {
                  field.setAccessible(true);
                  field.set(obj, service);
            } catch (IllegalArgumentException | IllegalAccessException e) {
                  e.printStackTrace();
            }          
      }
}

@Retention (RetentionPolicy.RUNTIME)
@Target (ElementType.FIELD)
public @interface Autowired {
}

```
**Pros:**
- Supports the Open-Closed principle, loose coupling, and dependency inversion
- Manage dependencies by configuration
- improves extensibility, flexibility, testability
- better readability

**Cons:** 
- hard learning curve
- shifts complexity to DI framework
- static analysis difficult
- **Fail at run time** instead of compile time