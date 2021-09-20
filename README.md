# GithubActionsExample

This is my simple Action that I'm currently using on my Android Projects

```
name: Android Build

on:
  push:
    branches: [ main ]
  pull_request: 
    branches: [ main ]

jobs:   
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2.3.4
        
      - name: Set up JDK 1.8
        uses: actions/setup-java@v1
        with:
          java-version: 1.8
          
      - name: Build with Gradle
        run: ./gradlew build
      
      - name: Run Tests
        run: ./gradlew test
        
      - name: Upload a Build Artifact (APK)
        uses: actions/upload-artifact@v2.2.4
        with:
          name: app
          path: app/build/outputs/apk/debug/app-debug.apk
```
