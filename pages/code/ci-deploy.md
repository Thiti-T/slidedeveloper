### CI-deploy

```ts {all|1-14|15-16}
name: Java CI

jobs:
  deploy:
    needs: build
    runs-on: ubuntu-latest
    steps:
    - name: executing remote ssh commands using ssh key
      uses: appleboy/ssh-action@v0.1.8
      with:
        host: ${{ secrets.HOST }}
        username: ${{ secrets.USERNAME }}
        key: ${{ secrets.KEY }}
        port: ${{ secrets.PORT }}
        script: |
          DEPLOY CMD
```

[Example](https://github.com/cpm-streaming-dev/kafka-streams-gradle/blob/master/.github/workflows/ci.yml)