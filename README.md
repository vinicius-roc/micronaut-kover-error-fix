## Micronaut grpc Application + Kover

Project to reproduce error on build Micronaut grpc Application with Kover plugin

## Checking tasks

Run command

```./gradlew clean build```

### Build tasks before Kover

- clean
- extractedIncludeProto
- extractProto
- generateProto
- processResources
- extractTestProto
- processTestResources
- kaptGenerateStubsKotlin
- kaptKotlin
- compileKotlin
- compileJava
- classes
- runnerJar
- buildLayers
- inspectClassesForKotlinIC
- jar
- startScripts
- distTar
- distZip
- shadowJar
- startShadowScripts
- shadowDistTar
- shadowDistZip
- assemble
- extractIncludeTestProto
- generateTestProto
- kaptGenerateStubsTestKotlin
- kaptTestKotlin
- compileTestKotlin
- compileTestJava
- testClasses
- test
- check

### Build tasks after Kover

- clean
- extractedIncludeProto
- extractProto
- generateProto
- processResources
- extractTestProto
- processTestResources
- kaptGenerateStubsKotlin
- kaptKotlin
- compileKotlin
- compileJava
- classes
- runnerJar
- buildLayers
- inspectClassesForKotlinIC
- jar
- startScripts
- distTar
- distZip
- shadowJar
- startShadowScripts
- shadowDistTar
- shadowDistZip
- assemble
- extractIncludeTestProto
- generateTestProto
- **generateResourcesConfigFile**
- kaptGenerateStubsTestKotlin
- **nativeCompile**
- kaptTestKotlin
- compileTestKotlin
- compileTestJava
- testClasses
- test
- **testNativeImage**
- Kover Tasks
- check

## Difference

We can see that with Kover plugin the build ran 3 tasks more than without plugin
- generateResourcesConfigFile
- nativeCompile 
- testNativeImage
