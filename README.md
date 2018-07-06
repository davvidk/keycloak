# Keycloak Howto

Based on: https://github.com/jboss-dockerfiles/wildfly


1 Run Dockerimage with Keycloak adapter 
```shell
docker run -p 8080:8080 -p 9990:9990 -it jboss/keycloak-adapter-wildfly /opt/jboss/wildfly/bin/standalone.sh -bmanagement 0.0.0.0
```
2 Get Container ID 

```shell 
docker ps
```

3 Add Admin user
```shell
docker exec -it <container-id> wildfly/bin/add-user.sh
```

3 Login to web-console
```shell
localhost:9990/console
```

# Build Dockerfile 

Build that image:

Look at the Dockerfile, build and run it. 

```shell 
docker build --tag=jboss/wildfly-admin .
```

Run it:
```shell 
docker run -p 8080:8080 -p 9990:9990 -it jboss/wildfly-admin
```

Login with:
```shell 
# username: admin
# password: admin
http://localhost:9990
```