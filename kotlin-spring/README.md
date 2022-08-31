```
./gradlew bootBuildImage --imageName=spring-hello-world
docker run --rm -p 8080:8080 spring-hello-world:latest
```