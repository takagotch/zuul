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
    String[] classNames = filterFileMangerConfig.getClassNames();
    
    assertEquals(3, filterLocations.length);
    assertEquals("outbound", filterLocations[1]);
    
    assertEquals(2, classNames.length);
    assertEquals("com.netflix.zuul.init.TestZuulFilter", classNames[0]);
    assertEquals("com.netflix.zuul.init2.TestZuulFilter2", classNames[1]);
  }
}

```

```
```

```
```



