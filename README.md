# chuck-norris-facts
Example repository for trying out Spring Boot 1.4.0 new features and enhancements

Running locally it expects a postgresql database, storing the chuck norris facts.

On OS X follow these steps to quickly setup postgresql using homebrew

```
$ brew update
$ brew install postgresql
$ postgres -D /usr/local/var/postgres  // start the server
```

new terminal window

```
$ createdb `mydb`
$ psql   // verify that you can connect to postgresql
```

The initial schema will be generated and populated using [Flywaydb](https://flywaydb.org) when the service starts.

Staring the service locally:

```
$ git clone https://github.com/altfatterz/chuck-norris-facts
$ cd chuck-norris-facts
$ ./gradlew clean build  // builds and runs the tests
$ java -jar build/libs/chuck-norris-facts-0.0.1-SNAPSHOT.jar --spring.profiles.active=postgres
```

in a new terminal

```
$ curl localhost:8080  // get a random chuck norris fact
{  
   "fact":"the movie 'Aliens vs Predators' was orginally supposed to be 'Aliens and Predators vs Chuck Norris' but that movie only lasted 8 seconds."
}
```

Follow the blog post: http://zoltanaltfatter.com/2016/04/16/trying-out-spring-boot-1.4.0-new-features-and-enhancements/




