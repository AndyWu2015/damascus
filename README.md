# Damascus

[![Build Status](https://travis-ci.org/yasuflatland-lf/damascus.svg?branch=master)](https://travis-ci.org/yasuflatland-lf/damascus)

Damascus is a Liferay Blade tool extension for generating scaffoldings of Service builder portlet with CRUD functionality based on a configuration json file, base.json. For more detailed usage, please see https://github.com/yasuflatland-lf/damascus/wiki

The list of what Damascus automatically generate is as follows
* CRUD functionality with a model
    * CRUD api / corresponding jsp pages
    * Document & Library access field (if you have a corresponding field in base.json)
    * Assets required field (if you have a corresponding field in base.json)
* Workflow
* Trashbox
* Search
* Comments
* Related assets
* Ratings
* Activities (The activities on the portlet will be recorded and visible on an activity portlet)
* Multiple service builder portlets at once
### Required enviroment
* Java 1.8 or above
* gradle 3.0 or above need to be installed
* jpm needs to be installed. (instruction to install is as follows)

### How to Install

**Mac**
```bash
curl https://raw.githubusercontent.com/yasuflatland-lf/damascus/master/installers/global | sudo sh
```

**Windows**
1. Download jpm (https://raw.githubusercontent.com/jpm4j/jpm4j.installers/master/dist/jpm-setup.exe) and install.
2. Install damascus.jar with jpm as follows. ```jpm install https://github.com/yasuflatland-lf/damascus/raw/master/latest/damascus.jar```

### How to update
1. Run ```jpm remove damascus``` to uninstall damascus.
2. Follow How to install section to install again

### Getting started
Let's make a Todo app with damascus
1. Create a Liferay workspace with Blade cli or Liferay IDE / Liferay Developer Studio. For more details, please see https://dev.liferay.com/develop/tutorials/-/knowledge_base/7-0/blade-cli
2. After creating Liferay workspace, navigate to under ```modules``` folder and run ```damascus -init Todo -p com.liferay.sb.test -v 70```
3. Navigate to ```Todo``` folder. You'll see ```base.json``` file is created. For detailed configuration, please see https://github.com/yasuflatland-lf/damascus/wiki Just for demonstration now, we'll create a scaffolding as it is.
4. Type ```damascus -create``` and damascus will create a scaffolding service and portlet according to the base.json file.
5. Start up your Liferay server and in the ```Todo``` folder, type ```blade deploy```. Blade will run properly and service and portlet will be deployed.

### How to complie Damascus on your own
1. Clone this repository to your local. Please make sure you've already installed Gradle 3.0 or above and jpm.
2. At the root directory, run ```gradle assemble``` then ```damascus.jar``` will be created under ```/build/libs/``` directory.
3. If you've already installed damascus, uninstall it first with ```jpm remove damascus```. Then install it with ```jpm install ./damascus.jar```.

### IDE settings
Damascus is including lombok library, so you need to configure annotations of lombok to be properly working and complied on IDEs. Here are how to apply lombok to Eclipse / IntelliJ
##### Eclipse
1. Download lombok https://projectlombok.org/download
2. double click ```lombok.jar``` and select the directory where ```eclipse.exe``` exist
3. Run ```gradle eclipse``` at the project directory and restart IDE, and right click on the project and display context name, and choose ```gradle > Refresh gradle project```
4. Java files will be displayed properly without errors.
##### IntelliJ
1. ```Preferences - Plugins``` and search Lombok. Install the Lombok plugin.
2. ```Preferences - Build, Execution, Deployment - Compiler - Annotation Processors``` and check ```Enable annotation processing```

### Bug reports / Enhancement requests
In terms of bugs, please post Github issues or send me a PR. In terms of a Enhancement request, please post a issue. Contribution is always welcome!

### What Damascus stands for?
Damascus is named after "Damascus blade", which is a strong / sharp blade made out from Damascus steel and forged with a lost technology. Liferay has it's official development tool,"Blade", so I gave this name in hope of reinforcement or extension of Blade tool.