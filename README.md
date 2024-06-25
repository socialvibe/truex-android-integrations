# true[X] Android / Fire TV Integrations

Documentation and reference apps for true[X]'s Android / Fire TV-based integration library. It is a common library that works across Android mobile, Androiv TV, and Fire TV platforms.

The current version of the integration API documentation can be found here: [TruexAdRenderer-Android Documentation](DOCS.md). It outlines how to use the TruexAdRenderer. Included within the documentation is a description of the public API for the TruexAdRenderer as well as a description of the event flow.

## Getting Started

The first step is to fetch the latest version of the TruexAdRenderer. The easiest way to add the TruexAdRenderer is via Maven. true[X] manages its Maven repository on Amazon S3.

### Adding the Renderer

In your app's `build.gradle`:

1. Under `repositories`, add a new maven entry with the url: <https://s3.amazonaws.com/android.truex.com/tar/prod/maven>
2. Under `dependencies`, add `implement 'com.truex:TruexAdRenderer-Android:2.8.2'`
    * Be sure to replace the version number with whatever the current latest one is.

#### Example app's build.gradle

```
apply plugin: 'com.android.application'

android {
    compileSdkVersion 30
    defaultConfig {
        applicationId "com.example.demoapp"
        minSdkVersion 17
        targetSdkVersion 30
        versionCode 1
        versionName "1.0"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
}

repositories {
    maven {
        url "https://s3.amazonaws.com/android.truex.com/tar/prod/maven"
    }
}

dependencies {
    implementation fileTree(include: ['*.jar'], dir: 'libs')
    implementation 'com.android.support:appcompat-v7:26.1.0'
    implementation 'com.truex:TruexAdRenderer-Android:2.8.2'
}
```

* * *

## Next Steps

### Mobile Example

Here is [a mobile example](https://github.com/socialvibe/truex-android-mobile-reference-app) of a minimal android application that uses the TruexAdRenderer.

Note in particular the [PlayerFragment](https://github.com/socialvibe/truex-android-mobile-reference-app/blob/master/ReferenceApp/src/main/java/com/truex/referenceapp/player/PlayerFragment.java#L274-L290) and [TruexAdManager](https://github.com/socialvibe/truex-android-mobile-reference-app/blob/master/ReferenceApp/src/main/java/com/truex/referenceapp/ads/TruexAdManager.java) classes that illustrate how to show an interactive TruexAd when encountering it on an ad break, and then resuming either the main video or else the fallback ad videos, depending on the user receiving an ad credit.

### Google Ad Manager (GAM) DAI SDK Integration Example

Here is a [reference application](https://github.com/socialvibe/truex-android-google-ad-manager-reference-app) that outlines how to use the Google Ad Manager (GAM) DAI SDK with the TruexAdRenderer.

### React Native Example

Here is a [reference application](https://github.com/socialvibe/Tinkerbell) that demonstrates how to use the renderer within a React Native application, by wrapping the renderer in a React module.
