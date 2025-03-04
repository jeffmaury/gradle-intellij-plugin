# Changelog

## 0.4.12

- More structured logging
- Introduced `intellij.useProductionClassLoaderInTests` option to control how plugin is going to be loaded in tests 

## 0.4.11

- Fix setting archive name for Gradle 5.1 and higher [#436](../../issues/436)  
- Fix forms compilation for Rider and Python snapshot builds. Works for Rider-2019.3-SNAPSHOT and higher [#403](../../issues/403)   

## 0.4.10

- Upgrade download plugin [#418](../../issues/418)
- Simplify custom runIde task configuration [#401](../../issues/401)


## 0.4.9

- Graceful handling of 404 errors when publishing a new plugin [#389](../../issues/389)
- Support PyCharm as an SDK
- Fail if the plugin depends on Java plugin but doesn't declare it as dependency

## 0.4.8

- Gradle 5.4 compatibility
- Support for new JBR distributions layout
- Made buildSearchableOption task incremental

## 0.4.7

- add one more executable file in Rider SDK

## 0.4.6

- support Gradle 5.3 [#379](../../issues/379)
- fixed downloading JBR 8 for IDEAE 2018.3 and earlier

## 0.4.5

- support JBR 11 from the new JetBrains Runtime Repo
- support running using JBR 11 [IDEA-208692](https://youtrack.jetbrains.com/issue/IDEA-208692)

## 0.4.4
- support the new bintray repository for JetBrains Runtime artifacts
- fixed downloading of old JBR  builds [#367](../../issues/367)
- fix instrumentation for local IDE instances [#369](../../issues/369)

## 0.4.3

- fixed downloading instrumentation dependencies for release versions
- fixed downloading renamed JetBrains Runtime artifacts

## 0.4.2

- fixed removing `config/` and `system/` on running `runIde` task [#359](../../issues/359)

## 0.4.1

- fixed plugin's sources attaching

## 0.4.0

- drop Gradle 2 support
- support for CLion as a building dependency [#342](../../issues/342)
- support token-based authentication while publishing plugins [#317](../../issues/317)
- add notification about patching particular tag values and attributes in plugin.xml [#284](../../issues/284)
- fix attaching sources to bundled plugins [#337](../../issues/337)
- fix verification message in case of default value of `description`-tag

## 0.3.12

- fixed resolving plugins from a custom channel [#320](../../issues/320)
- fixed building with Java 9

## 0.3.11

- ~~fixed resolving plugins from a custom channel~~
- fixed uploading plugins [#321](../../issues/321)
- fixed caching strategy for IDEA dependency [#318](../../issues/318)
 
## 0.3.10

- fixed dependency on local plugin files
- cache-redirector is used for downloading plugin dependencies [#301](../../issues/301) 

## 0.3.7

- fixed missing `tools.jar` on Mac [#312](../../issues/312)

## 0.3.6

- `runIde` task uses `tools.jar` from a JBRE java [#307](../../issues/307)

## 0.3.5

- Allow to override all system properties in RunIde task [#304](../../issues/304)
- Move to the new url to JBRE and Gradle distributions [#301](../../issues/301)
- Fixed an encoding while writing plugin.xml [#295](../../issues/295)

## 0.3.4

- Gradle 4.8 compatibility [#283](../../issues/283)

## 0.3.3

- fixed compiling JGoodies forms for IDEA version >= 182.* [#290](../../issues/290)

## 0.3.2

- use tools.jar from a java of `runIde` task [IDEA-192418](https://youtrack.jetbrains.com/issue/IDEA-192418)

## 0.3.1

- fix running for IDEA version < 2017.3 [#273](../../issues/273)

## 0.3.0

- added plugin verification task: `verifyPlugin`
- default values of `runIde` task are propagated to all RunIdeaTask-like tasks
- enhanced plugins resolution: better error messages for unresolved dependencies and fixes [#247](../../issues/247)
- check build number to decide whether the unzipped distribution can be reused (fixes [#234](../../issues/234))
- download JetBrains Java runtime and use it while running IDE (fixes [#192](../../issues/192))
- do not include plugin's jars recursively (fixes [#231](../../issues/231))
- allow to add custom Javac2.jar to `instrumentCode` task

## 0.2.20

- recognize new kotlin stdlib files as part of IDEA dependency

## 0.2.19

- Setup project plugin dependency for an already evaluated project (fixes [#238](../../issues/238))

## 0.2.18

- update default repository url
- support for running GoLand 

## 0.2.17

- fix compatibility with Gradle 4.0 new versions of Kotlin and Scala plugins (fixes [#221](../../issues/221) and [#222](../../issues/222))

## 0.2.16

- automatically set system properties for debugging Resharper

## 0.2.15

- restore scripts execution permissions in Rider distribution 

## 0.2.14

- support RD prefix for Rider
- avoid possible NPEs (fixes [#208](../../issues/208))

## 0.2.13

- Gradle 4.0 compatibility fixes

## 0.2.12

- upgrade plugin-repository-rest-client

## 0.2.11

- upgrade plugin-repository-rest-client

## 0.2.10

- upgrade plugin-services libraries to fix 'Invalid plugin type' exception while downloading plugins dependencies (fixes [#201](../../issues/201))
- prefer `compile` configuration for any plugins IDEA dependencies in tests (fixes [#202](../../issues/202))

## 0.2.9

- prefer `compile` configuration for bundled plugins IDEA dependencies in tests

## 0.2.8

- prefer `compile` configuration for IDEA dependencies in tests
- prefer `compileOnly` configuration for plugins dependencies in tests

## 0.2.7

- avoid exception due to adding duplicated configurations

## 0.2.6

- prefer `compileOnly` configuration for IDEA dependencies

## 0.2.5

- set `buildDir` as a default cache for IDE dependencies in case of Rider-plugin
- fix Kotlin instrumentation

## 0.2.4

- fixed attaching sources for IDEA Ultimate and bundled plugins

## 0.2.3

- fixed compilation for multi-module layout
 
## 0.2.2

- added `runIde` task. `runIdea` is deprecated now (fixes [#169](../../issues/169))
- fixed kotlin forms instrumentation (fixes [#171](../../issues/171))
- fixed filtering out all resources of dependent plugins (fixes [#172](../../issues/172))
- fixed intellij.systemProperties extension (fixes [#173](../../issues/173)) 

## 0.2.1

- added Rider support (fixes [#167](../../issues/167))
- fix unresolved builtin plugins on case-insensitive file systems

## 0.2.0

- result artifact format is changed: now it's always a ZIP archive even if plugin has no extra dependencies. *Note that this may change classloading (see [#170](../../issues/170))*
- added an ability to use local IDE installation for compiling
- result zip archive is added to `archives` configuration, built-in `assemble` task now builds the plugin distribution
- added JPS-type for intellij dependency (fixes [#106](../../issues/106))
- patchXml action is reimplemented, now it's possible to freely customize input files, destination directory, since/until builds, plugin description and version
- publishTask is reimplemented, now it's possible to set several channels to upload (fixes [#117](../../issues/117))
- reimplementation tasks also includes following improvements for all of them:
  - it's possible to reuse reimplemented tasks in client's code
  - it's allowed to run tasks without plugin.xml
  - tasks are configured before project evaluation, `project.afterEvaluate` is not require anymore
- fix incremental compiling after instrumenting code (fixes [#116](../../issues/116))
- added `intellij.ideaDependencyCachePath` option (fixes [#127](../../issues/127))
- `project()` reference can be used as a plugin-dependency (fixes [#17](../../issues/17))
- fix attaching sources of builtin plugins (fixes [#153](../../issues/153))

## 0.1

### 0.1.10

**Avoid using this version unless you have several plugin project which use the very same sandbox directory**

- Do not override plugins directory content (temporary fix of [#17](../../issues/17)) 

### 0.1.9

- Added default configuration to ivy-repositories (fixes [#114](../../issues/114))

### 0.1.6

- External plugin directories are placed in compile classpath so IDEA code insight is better for them now (fixes [#105](../../issues/105)) 

### 0.1.4

- Fix incremental compilation on changing `intellij.version` (fixes [#67](../../issues/67))

### 0.1.0

- Support external plugin dependencies

## 0.0

### 0.0.41

- Fix Kotlin forms instrumentation ([#73](../../issues/73))

### 0.0.39

- Allow to make single-build plugin distributions (fixes [#64](../../issues/64))

### 0.0.37

- Exclude kotlin dependencies if needed (fixes [#57](../../issues/57))

### 0.0.35

- Disable automatic updates check in debug IDEA (fixes [#46](../../issues/46))

### 0.0.34

- Support local IDE installation as a target application of `runIdea` task

### 0.0.33

- Attach community sources to ultimate IntelliJ artifact (fixes [#37](../../issues/37))
- New extension for passing system properties to `runIdea` task (fixes [#18](../../issues/18))

### 0.0.32

- Support compilation in IDEA 13.1 (fixes [#28](../../issues/28))

### 0.0.30

- Fixed broken `runIdea` task

### 0.0.29

- `cleanTest` task clean `system-test` and `config-test` directories (fixes [#13](../../issues/13))
- Do not override plugins which were installed in debug IDEA (fixes [#24](../../issues/24))

### 0.0.28

- `RunIdeaTask` is extensible (fixes [#23](../../issues/23))
- Fix xml parsing exception (fixes [#25](../../issues/25))

### 0.0.27

- Disabled custom class loader in tests (fixes [#21](../../issues/21))

### 0.0.25

- Do not patch version tag if `project.version` property is not specified (fixes [#11](../../issues/11))

### 0.0.21

- IntelliJ-specific jars are attached as compile dependency (fixes [#5](../../issues/5))

### 0.0.10

- Support for attaching IntelliJ sources in IDEA
