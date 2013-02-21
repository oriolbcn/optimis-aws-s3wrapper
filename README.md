# Amazon S3 Wrapper for OPTIMIS

AWSS3Wrapper.
1.0.0-SNAPSHOT.
20.02.2013.

## License and Copyright

Copyright [2013] [Oriol Collell Martin]

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

## Introduction

The Amazon S3 Wrapper component is part of the OPTIMIS Europeran research project (http://www.optimis-project.eu/) and it is used
by the Data Manager to upload service images to Amazon S3. Once this component is integrated with the Data Manager it could be
used to automatically upload images to Amazon when performing a bursting operation to it. Images uploaded by this component are stored
in a bucket per service. A bucket uniquely identifies a service by including its id in its name, so that images can be easily retirieved later
on by just providing the id of the service and the name of the image.

We have used the Java AWS SDK to implement this component. More information about the SDK can be found in http://aws.amazon.com/es/sdkforjava/

## Functions

This component implements the following functionality:
* Upload Image: Uploads a service or data image to Amazon S3.
* Download Image: Downloads a service or data image from Amazon S3.
* List Images: Lists all images uploaded for a service.
* Delete Image: Deletes an image uploaded for a service.

## Using the Software
This component can be tested in isolation by executing the test GUI that is provided with it. However, the component it is only relevant in conjuction
with a full OPTIMIS deployment.

You need an AWS account to be able to use this software. The access and secret keys have to be specified in a configuration file with the follwing contents:
```
AWSAccessKey=<Your AWS Access Key here>
AWSSecretKey=<Your AWS Secret Key here>
```

The path of this file has to be passed as a paramter to the GUI application by using the "-c <path>" argument.

### Software Dependencies

This component has been written in Java, therefore it needs a JVM to run. We have used Maven to manage the dependencies and build process of the project,
therefore, you will need to have Maven installed too.

Dependencies with libraries external to OPTIMIS are described in the POM.


### Installation and Execution Instructions

The test GUI of this component can be installed by running the `mvn clean install assembly:single` command on the project root. This generates a ".jar" file with
all the compiled code and dependencies in the "target" directory. This jar file can then be executed by running `java -jar [jar_file] -c <conf_path>`

This test GUI consist on a very simple GUI that contains a set of controls to Upload, Download, List and Delete images.


## Contributors
Oriol Collell Martin

## Contact Information and Website

http://www.optimis-project.eu/

We welcome your feedback, suggestions and contributions. Contact us
via email if you have questions, feedback, code submissions, 
and bug reports.

For general inquiries, see http://www.optimis-project.eu/contact

You can submit bug, patches, software contributions, and feature 
requests using Bugzilla.  
Access Bugzilla at: 
http://itforgebugzilla.atosresearch.eu/bugzilla/enter_bug.cgi?product=Optimis 
