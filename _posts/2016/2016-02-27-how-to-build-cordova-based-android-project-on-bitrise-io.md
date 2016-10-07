---
layout: post
title: How to build Cordova-based Android project on bitrise.io
date: 2016-02-27 15:14:23
comments: true
categories: [android, cordova, bitrise.io]		
tags: [android, cordova, bitrise.io]
---

[Bitrise](http://bitrise.io) is a Mobile Continuous Integration and Delivery service. It has a lot of [integrations](https://www.bitrise.io/integrations) and the number of integrations increases very fast. The best thing about integrations is that they are completely `open source`.

#### **Prehistory**

Bitrise provides range of [stacks](http://devcenter.bitrise.io/docs/available-stacks), and you can decide which one to choose for your project. I'm doing Android development and everything related to Android is automatically interesting to me.
I wanted to contribute to [bitrise-steps](https://github.com/bitrise-io/bitrise-steplib) something related to Android. Inspiration came from [bitrise-user-voice](https://bitrise.uservoice.com) and I've chosen [**Install Cordova and Ionic**](https://bitrise.uservoice.com/forums/235233-general/suggestions/9285630-install-cordova-and-ionic). Both `Cordova` and `Ionic` platforms were new to me, which even more increased my interest.

<!--more-->

As all Android jobs on [bitrise.io](http://bitrise.io) are running in isolated `docker` containers, all what I needed to do is to extend existing [bitrise docker images](https://github.com/bitrise-docker) and add Cordova support.

It took me 2-3 weeks to prepare docker image for [bitrise.io](http://bitrise.io) with Cordova related dependencies installed. It's a bit long period of time, as I had problems with freezing docker containers on my local PC (every time when `cordova build` command was executed, I've got frozen docker container). I've tested my docker image on Mac OS a lot - and got frozen container on `cordova build`. Than I've configured `ubuntu-14.04` using `Vagrant`, installed docker in ubuntu-14.04 VM - same effect. But I knew that configuration is ok, as I read tons of articles about docker images already, checked some other docker images which have Cordova related dependencies.

Finally, I've published [docker-android-cordova](https://hub.docker.com/r/vgaidarji/docker-android-cordova/) image to [Docker Hub](https://hub.docker.com) and decided to give a last try to my docker image at [bitrise.io](http://bitrise.io). And it worked! :open_mouth:

<img src="/assets/2016/02/27/david-blane.png" alt="David Blane"/>

#### **How to build Cordova-based Android project on bitrise.io using dedicated docker image**


1. Add your Cordova Android project to bitrise.io (["+ Add new app"](https://www.bitrise.io/apps/add) button).

    <img src="/assets/2016/02/27/add-new-app.png" alt="Add new app"/>
2. Follow the steps and add your application. In this case I'm using [Cordova Android Sample](https://github.com/vgaidarji/cordova-android-sample) application. It's a default Android application generated with `cordova create` command + some cordova android plugins.

    <img src="/assets/2016/02/27/add-new-app-screen.png" alt="Add new app 2"/>
3. At `"Project build configuration"` step choose `"Configure it manually"` and select Android platform.

    <img src="/assets/2016/02/27/project-build-config-manual.png" alt="Project build config manual"/>
4. Enter following parameters (see screenshot). The only important information here is the branch name. We'll modify or even delete Gradle tasks further in workflow configuration. Pressing `"I'm ready"` should finish project configuration process.

    <img src="/assets/2016/02/27/project-build-config-params.png"   alt="Project build config params"/>
5. Navigate to project `"Settings"` tab.

    <img src="/assets/2016/02/27/cordova-project-settings.png"   alt="Cordova project settings"/>
6. Scroll down to stacks section and enter `vgaidarji/docker-android-cordova:latest` into `"Docker image to use"`. This is my custom docker image which has all required tools listed for Cordova Android projects.

    <img src="/assets/2016/02/27/stacks-section.png"   alt="Stacks section"/>
7. Go to `"Workflow"` tab and select `"Manage workflows"`

    <img src="/assets/2016/02/27/workflow-primary.png"   alt="Stacks section"/>
8. In "edit mode" remove default `"Gradle"` step, and add `"Cordova Android"` between `"Git clone repository"` and `"Deploy to bitrise.io"` steps.

    <img src="/assets/2016/02/27/remove-gradle-step.png"   alt="Remove gradle step"/>

    <img src="/assets/2016/02/27/add-cordova-step.png"   alt="Add cordova step"/>   
9. By default, `"Cordova Android"` step will execute following command <br> `cordova build android --verbose`. Feel free to modify parameters. To be honest, I didn't test all the commands, but they should work for sure.

    <img src="/assets/2016/02/27/cordova-step-config.png"   alt="Cordova step config"/>   
10. Press `"Save"` button at left. Now we're ready to build our project.

    <img src="/assets/2016/02/27/save-config.png" alt="Save config"/>   
11. Navigate to `"Builds"` tab and press `"Start build"`. The build will use our default workflow, with `"Cordova Android"` step, and if everything is ok, you should see something like:

    <img src="/assets/2016/02/27/build-success.png" alt="Build success"/>

    Configurations! We did it! :beer: + :pizza:  

**Note:** The one thing is that in this example we use custom docker image in order to build "Cordova Android" project at bitrise.io. In the near future, all Cordova related tools will be preinstalled in [bitrise-base](https://github.com/bitrise-docker/bitrise-base) and/or [bitrise-android](https://github.com/bitrise-docker/android) docker images. It means that we'll not need anymore additional docker image and "Cordova Android" projects should be supported by default.
