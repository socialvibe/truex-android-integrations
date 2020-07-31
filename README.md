# true[X] Android/Fire TV Integrations

Documentation and reference apps for true[X]'s Android/Fire TV-based integration library.

The current version of the integration documentation can be found here: [TruexAdRenderer-AndroidTV Documentation](DOCS.md).

## Getting Started

The first step is to fetch the latest version of the TruexAdRenderer. The easiest way to add the TruexAdRenderer is via Maven. true[X] manages its Maven repository on Amazon S3.

### Adding the Renderer

In your app's `build.gradle`:

1. Under `repositories`, add a new maven entry with the url: <https://ctv.truex.com/android/maven>
2. Under `dependencies`, add `compile 'com.truex:TruexAdRenderer-tv:2.1.3'`

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
        url "https://ctv.truex.com/android/maven"
    }
}

dependencies {
    implementation fileTree(include: ['*.jar'], dir: 'libs')
    implementation 'com.android.support:appcompat-v7:26.1.0'
    implementation 'com.truex:TruexAdRenderer-tv:2.1.3'
}
```

* * *

## Next Steps

### Integration Example

Here is [an example][sheppard] of a minimal android application that uses the TruexAdRenderer.

### Google Ad Manager (GAM) DAI SDK Integration Example

Here is a [reference application](https://github.com/socialvibe/truex-android-google-ad-manager-reference-app) that outlines how to use the Google Ad Manager (GAM) DAI SDK with the TruexAdRenderer.

### Integration Documentation

The [TruexAdRenderer documentation][docs] outlines how to use the TruexAdRenderer. Included within the documentation is a description of the public API for the TruexAdRenderer as well as a description of the event flow.

[sheppard]: https://github.com/socialvibe/sheppard
[gam]: https://github.com/socialvibe/truex-tvos-google-ad-manager-reference-app
[docs]: https://github.com/socialvibe/truex-androidtv-integrations/blob/develop/DOCS.md