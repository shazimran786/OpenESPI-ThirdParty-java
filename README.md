[![Build Status](https://travis-ci.org/energyos/OpenESPI-ThirdParty-java.png)](https://travis-ci.org/energyos/OpenESPI-ThirdParty-java)

OpenESPI-ThirdParty
======================

The Open Energy Services Provider Interface (ESPI) Third Party Repository Providing implementations of the interface used to provide energy usage information to retail customers.

## Setup

Note: You need to download and install [OpenESPI-Common-Java](https://github.com/energyos/OpenESPI-Common-java) into your local Maven repository to build this project.

First clone the project from github:

```bash
git clone https://github.com/energyos/OpenESPI-ThirdParty-java.git
cd OpenESPI-ThirdParty-java/
```

Build and start tomcat7 using maven (note: you must have first built the OpenESPI-Common-java jar):

```bash
mvn tomcat7:run
```

Now the application should be available at [http://localhost:9000/](http://localhost:9000/).


## Building
```bash
# for the default test profile
mvn clean install

# or for a specific profile
mvn -P <profile name> -Dmaven.test.skip=true clean install
```


## IDE Setup

### Eclipse Setup

Open Eclipse and import a Maven project (File > Import... > Maven > Existing Maven Projects).

### Spring Tool Suite Setup

Open Spring Tool Suite and import a Maven project (File > Import... > Maven > Existing Maven Projects).

To Run from within STS:

right click on project and select RunOnServer


To run the DC and/or the TP:

do a maven build and install accordingly. Then the WAR files will be in the right position.

To Start server:

```bash
sudo /home/bitnami/springsource/vfabric-tc-server-developer-2.9.3.RELEASE/base-instance/bin/tcruntime-ctl.sh start
```
To Stop server:

```bash
sudo /home/bitnami/springsource/vfabric-tc-server-developer-2.9.3.RELEASE/base-instance/bin/tcruntime-ctl.sh stop
```

### IntelliJ Setup

Open IntelliJ and open the project (File > Open...).

## Testing

### Unit Tests

To run all Unit tests:

```bash
mvn test
```

Run a single test class:

```bash
mvn -Dtest=<TestClassName> test
mvn -Dtest=HomeControllerTests test
```

Run a single test in a single class:

```bash
mvn -Dtest=<TestClassName>#<testMethodName> testMethodName
mvn -Dtest=HomeControllerTests#index_whenNotLoggedIn_displaysHomeView test
```

### Cucumber Features

To run all Cucumber features:

```bash
mvn verify
```

