# Simple Java Springboot application
Simple java springboot application
endpoint :8080/health should answer "UP".
To build jar please use:

```
docker run -it --rm --name my-maven-project -v C:\DiskD\Study\Epam\Docker\projects\java_app:/usr/src/app -v %UserProfile%/.m2:/root/.m2 -w /usr/src/app maven:3.6-jdk-8 mvn clean package
```

```
docker run -it --rm --name my-maven-project -v "$PWD":/usr/src/app -v "$HOME"/.m2:/root/.m2 -w /usr/src/app maven:3.6-jdk-8 mvn clean package
```
Application can take environment variables:
```
DB_MYSQL_HOST: "mysqlhost"
DB_MYSQL_PORT: 3306
DB_MYSQL_NAME: "testdb"
DB_MYSQL_USER: root
DB_MYSQL_PASS: "123456aA"
```
Use this app to conver .sh file to Unix format
https://waterlan.home.xs4all.nl/dos2unix.html

### HOMEWORK
1. Build jar file from sources https://github.com/danuf/java_app using maven container maven:3-jdk-8
2. Write docker-compose.yaml which contains mysql database container and application container:
- Use mysql/mysql-server:5.7 image
- Specify mysql_database, mysql_root_password, and mysql_root_host env variables for mysql cotainer
- Application container should use “build:” instruction in compose file
- Link containers to each other
- Specify memory limits for each container
- Pass parametes through env variables for application container like this:
  - DB_MYSQL_HOST: "mysqldb"
  - DB_MYSQL_PORT: 3306
  - DB_MYSQL_NAME: "testdb"
  - DB_MYSQL_USER: root
  - DB_MYSQL_PASS: "123456aA"
- Expose application container to 80 port of localhost
3. Run docker-compose and sure that app container is connected to db. Check logs
4. Provide configuration file (docker-compose.yaml) and screenshot of web interface as prove result of homework