## Docker Image for Android CI
You can use this image for building your Android app within your CI.

-----

## Usage in GitLab CI

```yaml
image: Rokib-Uddin/android_ci

before_script:
    - chmod +x ./gradlew
    
stages:
    - build

cache:
  paths:
    - .gradle/wrapper
    - .gradle/caches

assembleDebug:
    stage: build
    script:
        - ./gradlew assembleDebug
        - cp app/build/outputs/apk/debug/app-debug.apk app-debug.apk
    artifacts:
        paths:
            - app-debug.apk
           
```
