#Welcome to the Source code of MIT App Inventor

##Introduction

Learn more about [MIT App Inventor](http://appinventor.mit.edu).

This code is designed to be run in Google's App Engine. MIT runs a
public instance that all are welcome to use to build App Inventor
Applications. You do not need to compile or use this code if you wish
to build MIT App Inventor applications.

We provide this code for reference and for experienced people who wish
to operate their own App Inventor instance.

This code is tested and known to work with Oracle Java 6 and 7. There might be some issues with using OpenJDK.

##Setup instructions

This is a quick guide to get started with the sources. More detailed instructions can be found [here](https://docs.google.com/document/pub?id=1Xc9yt02x3BRoq5m1PJHBr81OOv69rEBy8LVG_84j9jc), a slide show can be seen here, and all the [documentation](http://appinventor.mit.edu/appinventor-sources/#documentation) for the project can be found in our [site](http://appinventor.mit.edu/appinventor-sources/).

###Dependencies
You will need a full Java JDK (6 or 7, preferably from Oracle; JRE is not enough) and Python to compile and run the servers.

You will also need a copy of the [App Engine SDK](https://developers.google.com/appengine/downloads) for Java and [ant](http://ant.apache.org/).

If you want to make changes to the source, you are going to need to run an automated test suite, and for that you will also need [phantomjs](http://phantomjs.org/). Have a look at the testing section for more information.

###Forking or cloning
Consider ***forking*** the project if you want to make changes to the sources. If you simply want to run it locally, you can simply ***clone*** it.

####Forking
If you decide to fork, follow the [instructions](https://help.github.com/articles/fork-a-repo) given by github. After that you can clone your own copy of the sources with:

    $ git clone https://github.com/YOUR_USER_NAME/appinventor-sources.git

Make sure you change *YOUR_USER_NAME* to your user name.

Configuring a remote pointing to this repository is also a good idea if you are forking:

    $ cd appinventor-sources
    $ git remote add upstream https://github.com/mit-cml/appinventor-sources.git

Finally, you will also have to make sure that you are ignoring files that need ignoring:

    $ cp sample-.gitignore .gitignore


###Compiling
Compiling is very easy if you have all the dependencies you need; just open a terminal and type:

    $ cd appinventor
    $ ant

You will see a lot of stuff in the terminal and after a few minutes (it can take from 2 to 10 minutes, depending on your machine specs) you should see a message saying something like *Build Successful*.

###Running the server(s)
There are two servers in App Inventor, the main server that deals with project information, and the build server that creates apk files. More detailed information can be found in the [App Inventor Developer Overview](https://docs.google.com/document/d/1hIvAtbNx-eiIJcTA2LLPQOawctiGIpnnt0AvfgnKBok/pub) document.

####Running the main server

    $ your-appengine-SDK-folder/bin/dev_appserver.sh
            --port=8888 --address=0.0.0.0 appengine/build/war/

Make sure you change *your-appengine-SDK-folder* to wherever in your hard drive you have placed the App Engine SDK.

####Running the build server
The build server can be run from the terminal by typing:

    $ cd appinventor/buildserver
    $ ant RunLocalBuildServer

Note that you will only need to run the build server if you are going to build an app as an apk. You can do all the layout and programming without having the build server running, but you will need it to download the apk.

###Accessing your local server
You should now be up and running; you can test this by pointing your browser to:

    http://localhost:8888

###Running tests
The automated tests depend on [Phantomjs](http://phantomjs.org/). Make sure you install it and add it to your path. After that, you can run all tests by typing the following in a terminal window:

    $ ant tests


##Contributing to the project
check out our open source [site](http://appinventor.mit.edu/appinventor-sources/) to get a lot more information about the project and how to contribute to it.

##Need help?
Contact us through our [Google Group](https://groups.google.com/forum/#!forum/app-inventor-open-source-dev) or [G+ community](https://plus.google.com/u/0/b/116831753302186936352/116831753302186936352/posts).