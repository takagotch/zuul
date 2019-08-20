### zuul
---
https://github.com/Netflix/zuul

```java
// zuul-core/src/test/java/com/netflix/zuul/init/ZuulFiltersModuleIntegTest.java

@RunWith(GovernatorJunit4ClassRunner.class)
@ModulesForTesting({ZuulFiltersModule.class})
public class ZuulFiltersModuleIntegTest {
  @Inject
  FilterFileManagerConfig filterFileManagerConfig;
  
  @BeforeClass
  public static void before() {
    AbstractConfiguration configuration = ConfigurationManager.getConfigInstance();
    configuration.setProperty("zuul.filters.locations", "inbound,outbound,endpoint");
    configuration.setProperty("zuul.filters.packages", "com.netflix.zuul.init,com.netflix.zuul.init2")
  }
  
  @Test
  public void scanningWorks() {
    String[] filterLocations = filterFileManagerConfig.getDirectories();
    
  }
}

```

```
```

```
```



