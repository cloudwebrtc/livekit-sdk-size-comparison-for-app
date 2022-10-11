# livekit-sdk-size-comparison-for-app


# Android

app/build.gradle

```
    buildTypes {
        release {
            minifyEnabled true #Set to true here
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
            ndk {
                abiFilters "arm64-v8a" # only arm64
            }
        }
        debug {
            ndk {
                abiFilters "arm64-v8a"
            }
        }
    }
    
.....
    # add dependencies
    implementation("io.livekit:livekit-android:1.1.3") {
        exclude group: 'com.github.webrtc-sdk', module: 'android'
        exclude group: 'androidx.compose.ui', module: 'ui'
    }
    api 'com.github.webrtc-sdk:android-test:104.5112.01'
```

# iOS

open `uikit-minimal-dev.xcworkspace`

Add Packages Dependencies, Add Localation `https://github.com/livekit/client-sdk-swift.git` branch `for-binary-size-optimization`

