## Gradle

###### Gradle DSL method not found: 'runProguard()'
Replace `runProguard` with `minifyEnabled`
[source](http://stackoverflow.com/questions/27016385/error26-0-gradle-dsl-method-not-found-runproguard)

###### Missing proguard-rules.txt
When generating a signed APK, you get proguard-rules.txt is missing. Use below code as long as you don't need any special ProGuard configuration: [source](http://stackoverflow.com/questions/28258449/cant-generate-signed-apk-in-android-studio-because-proguard-rules-txt-is-missi)

```
buildTypes {
    release {
        minifyEnabled true
        proguardFiles getDefaultProguardFile('proguard-android.txt')
    }
}
```