### CI-Example

```ts {all|1-13|14-25|all}
name: Java CI

on:
  push:
    branches: [develop, release]
  pull_request:
    branches: [master]
  workflow_dispatch:

  env:
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: Set up JDK 17
      uses: actions/setup-java@v3
      with:
        java-version: '17'
        distribution: 'temurin'
        cache: gradle

    - name: Validate Gradle wrapper
      uses: gradle/wrapper-validation-action@e6e38bacfdf1a337459f332974bb2327a31aaf4b

    - name: Run chmod to make gradlew executable
      run: chmod +x ./gradlew

    - name: Build with Gradle
      uses: gradle/gradle-build-action@67421db6bd0bf253fb4bd25b31ebb98943c375e1
      with:
        arguments: build

    - name: Archive test report
      uses: actions/upload-artifact@v3
      with:
        name: Test report
        path: app/build/reports/tests/test

    - name: Log in to the Container registry
      uses: docker/login-action@f054a8b539a109f9f41c372932f1ae047eff08c9
      with:
        registry: ${{ env.REGISTRY }}
        username: ${{ github.actor }}
        password: ${{ secrets.GHCR_TOKEN }}

    - name: Extract metadata (tags, labels) for Docker
      id: meta
      uses: docker/metadata-action@98669ae865ea3cffbcbaa878cf57c20bbf1c6c38
      with:
        images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}

    - name: Build and push Docker image
      uses: docker/build-push-action@ad44023a93711e3deb337508980b4b5e9bcdc5dc
      with:
        context: .
        push: true
        tags: ${{ steps.meta.outputs.tags }}
        labels: ${{ steps.meta.outputs.labels }}


```