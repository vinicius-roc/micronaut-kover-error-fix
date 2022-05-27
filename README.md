## Micronaut grpc Application + Kover

Project to reproduce error on build Micronaut grpc Application with Kover plugin

## The problem

When you run command 

```./gradlew clean build```

with Kover plugin, the build ran 3 tasks more than without plugin

- generateResourcesConfigFile
- nativeCompile
- testNativeImage

This happens because, how explained [in this issue](https://github.com/Kotlin/kotlinx-kover/issues/185#issuecomment-1139427287) 
Kover automatically adds instrumentation to all tasks with the type org.gradle.api.tasks.testing.Test (JVM tests) and 
runs these tests while verification. It seems that in Micronaut native tests are run by a task with the type Test.

## How to fix

To disable the instrumentation of the testNativeImage task, you can add the following code (example for build.gradle.kts file)

```
tasks.withType<Test> {
    if (name == "testNativeImage") {
        extensions.configure(kotlinx.kover.api.KoverTaskExtension::class) {
            isDisabled = true
        }
    }
}
```