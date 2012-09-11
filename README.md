Cordova implementation for Tizen
===

Cordova implementation for Tizen is a JavaScript Wrapper library allowing to build and run Cordova based projects on [Tizen](https://www.tizen.org/).
Cordova based applications are, at the core, an application written with web technology: HTML, CSS and JavaScript.

Apache Cordova is an effort undergoing incubation at The Apache Software Foundation (ASF), sponsored by the Apache Incubator project. Incubation is required of all newly accepted projects until a further review indicates that the infrastructure, communications, and decision making process have stabilized in a manner consistent with other successful ASF projects. While incubation status is not necessarily a reflection of the completeness or stability of the code, it does indicate that the project has yet to be fully endorsed by the ASF.

Pre-requisites
---
 - [Tizen SDK 1.0 Larkspur Release](https://developer.tizen.org/sdk)

Directory Structure
---
    /tizen
        /samples ..... Ready-to-run Tizen Eclipse IDE sample projects
        /templates ... Cordova Tizen SDK projects templates for Tizen Eclipse IDE
        /www ......... Barebones project assets

Import a Cordova Tizen project sample into Tizen Eclipse IDE
----

1. File -> Import
2. Select Import Source: Widget -> Projects and Widget file -> Next
3. Import Widget -> Select root directory: Point to the one of the sample projects (e.g: /cordova-basic) -> Finish
4. The project should be available now in the Tizen Eclipse IDE Project Explorer
5. You can now go to the [Build and Deploy a project] section of this document


Install Cordova Tizen project templates into Tizen Eclipse IDE
----
1. Copy the entire /templates directory content into you Tizen Eclipse IDE web templates directory (e.g: /home/my_username/tizen-sdk/IDE/Templates/web)
2. You can now create Cordova Tizen project by using Tizen Eclipse IDE project templates

Create a project with the Tizen Eclipse IDE Cordova Tizen project templates
----
1. File -> New -> Tizen Web Project.
2. Select: User Template.
3. Select: User defined.
4. Select one of the Cordova templates, fill the Project Name, then -> Finish.
5. The project should be available now in the Tizen Eclipse IDE Project Explorer
6. You can now go to the [Build and Deploy a project] section of this document

Build and Deploy a project
----
1. Select and Right click the project -> Select Build project, this will generate your project widget package (.wgt)
2. Select and Right click the project -> Run As -> Here you can choose:
 - Tizen Web Simulator application
 - Tizen Web application (this will deploy you application to a pre-launched Tizen emulator or a Tizen connected device)

Barebones project assets
----

The `www` folder contains the Cordova specific assets that must be available in a Tizen Web project to make it 'Cordova enabled'.
If you have an existing Tizen Web application project, copy/merge these files into its root directory.

    /www
        config.xml .............. Tizen configuration file
        cordova-x.y.z.js ........ Tizen Cordova JavaScript API implementation library
        /sounds
            beep.wav ............ Needed for Cordova Notification API implementation

Add the following lines into the `<head>` section of your `index.html` project file:

    <script type="text/javascript" src="js/cordova.x.y.z.js"></script>

`config.xml` is a sample that you are free to alter or merge with an existing Tizen configuration file.
It contains the `<feature>` elements required by the Cordova API.
 
Further Reading
---

- [Cordova home](http://incubator.apache.org/cordova/)
- [Cordova Documentation](http://docs.cordova.io)
- [Cordova Issue Tracker](https://issues.apache.org/jira/browse/CB)
- [Tizen Web SDK Documentation](https://developer.tizen.org/documentation)

that could become the source for the apache incubator-cordova-tizen that is until now  empty 

framework/

    - cordova icon, for tizen we are not quite sure about the size to use...now it is a 64*64 png
    - inedx html, a starter html file 
    - tizen.css, for notifications UI
    - sounds/ beep.wav ,, a file that should be used by notifications to play a "beep"

js/
 where to put generated files from the cordova jake

lib/
    cordova.js, generated by make file

tizen SDK Samples/

mobile-spec/

a tizen SDK eclipse project (to be imported using Eclipse import wizard)

taken from after 2.0.0 tag

the cordova Legacy App slightly adapte to tizen :
    notifications/index.html is loading the tizen.css file for notifications
    (waiting to generate this from the source code)
    
    config.xml that is granting all tizen related features as mùmost of them are required by the Codova JavaScript lib
    
    there will be more sample soon :
    (actually tizen sample ported to phone gap when is makes sense, first should be contacts samples)