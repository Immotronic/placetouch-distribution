# Placetouch Distribution

Maven POMs and configuration files to generate installable distributions of the 
[Ubikit](http://www.ubikit.org) project


## Compilation

To generate distributions, you will need Maven 2 or later. The project POM rely on a 
parent POM. You will need to download and install this file in appropriate directory on 
your developpement machine.

- [Download the root POM](http://www.ubikit.org/resources/misc/maven/root-pom.xml)

### Tuning the root POM
At least, you need to adapt the "Distribution Management" section of the root POM to your 
developpement environment.

- If you do not wish to use a personal repository proxy server, simply remove the whole
<distributionManagement> element from root-pom.xml file.
- To use a personal repository procy server instead of Immotronic one, adapt <repository> and
<snapshotRepository> elements to match your configuration.

### Generation of a distribution for a desktop (Linux or Mac OSX) environment

Use the following command:

	mvn -f Desktop-pom.xml package

This command will generate a distribution archive 
(`placetouch-distribution-Desktop-1.13.0-SNAPSHOT.zip`) available in the `target/` 
directory.


### Generation of a distribution for the Raspberry Pi

Use the following command:

	mvn -f RaspberryPi-pom.xml package

This command will generate a distribution archive 
(`placetouch-distribution-RaspberryPi-1.13.0-SNAPSHOT.zip`) available in the `target/` 
directory.


## How to run the framework

- Copy the distribution archive (`placetouch-distribution-*-1.13.0-SNAPSHOT.zip`) on the 
on the host you wish to run it.
- Unzip the distribution archive.
- Change directory for `placetouch-distribution-*-1.13.0-SNAPSHOT/`

**Do the following step only if you are running the desktop distribution on Linux**

- Edit the `scripts/launch`file, comment settings that were suitable for OSX, and uncomment 
those for Linux.


- Launch the framework with the following command line:

    ./scripts/launch


 Then, you could access the framework UI at `http://localhost:8080/` (username = admin, password =
  password), and the OSGi web console at `http://localhost:8080/system/console (username = admin, 
  password = admin)

 