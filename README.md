<p align="center">
  <img id="header" src="./images/logo_dockerandroid_small.png" />
</p>

[![Join the chat at https://gitter.im/butomo1989/docker-android](https://badges.gitter.im/butomo1989/docker-android.svg)](https://gitter.im/butomo1989/docker-android?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/butomo1989/docker-android.svg?branch=master)](https://travis-ci.org/butomo1989/docker-android)
[![codecov](https://codecov.io/gh/butomo1989/docker-android/branch/master/graph/badge.svg)](https://codecov.io/gh/butomo1989/docker-android)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/3f000ffb97db45a59161814e1434c429)](https://www.codacy.com/app/butomo1989/docker-appium?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=butomo1989/docker-appium&amp;utm_campaign=Badge_Grade)

Docker-Android is a docker image built to be used for everything related to mobile website testing and Android project.

<p align="center">
   <a href="https://youtu.be/pQdpjuYwvp8"><img src="./images/appiumconf2018.png" alt="Appium Conference 2018" width="600"></a>
</p>

Emulator - Samsung Device    | Emulator - Nexus Device     | Real Device  
:---------------------------:|:---------------------------:|:---------------------------:
![][emulator samsung]        |![][emulator nexus]          |![][real device]   

Purposes
--------

1. Run UI tests for mobile websites with [appium]
2. Build Android project and run unit tests with the latest build-tools
3. Run UI tests for Android applications with different frameworks ([appium], [espresso], [robotium], etc.)
4. Run monkey / stress tests
5. SMS testing

Advantages compare with other docker-android projects
-----------------------------------------------------

1. noVNC to see what happen inside docker container
2. Emulator for different devices / skins, such as Samsung Galaxy S6, LG Nexus 4, HTC Nexus One and more.
3. Ability to connect to Selenium Grid
4. Ability to control emulator from outside container by using adb connect
5. Support real devices with screen mirroring
6. Ability to record video during test execution for debugging
7. Integrated with other cloud solutions, e.g. [Genymotion Cloud](https://www.genymotion.com/cloud/)
8. Open source with more features coming

List of Docker images
---------------------

|OS   |Android   |API   |Browser   |Browser version   |Chromedriver   |Image   |Size   |
|:---|:---|:---|:---|:---|:---|:---|:---|
|Linux|5.0.1|21|browser|37.0|2.21|butomo1989/docker-android-x86-5.0.1|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-x86-5.0.1.svg)](https://microbadger.com/images/butomo1989/docker-android-x86-5.0.1 "Get your own image badge on microbadger.com")|
|Linux|5.1.1|22|browser|39.0|2.13|butomo1989/docker-android-x86-5.1.1|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-x86-5.1.1.svg)](https://microbadger.com/images/butomo1989/docker-android-x86-5.1.1 "Get your own image badge on microbadger.com")|
|Linux|6.0|23|browser|44.0|2.18|butomo1989/docker-android-x86-6.0|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-x86-6.0.svg)](https://microbadger.com/images/butomo1989/docker-android-x86-6.0 "Get your own image badge on microbadger.com")|
|Linux|7.0|24|chrome|51.0|2.23|butomo1989/docker-android-x86-7.0|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-x86-7.0.svg)](https://microbadger.com/images/butomo1989/docker-android-x86-7.0 "Get your own image badge on microbadger.com")|
|Linux|7.1.1|25|chrome|55.0|2.28|butomo1989/docker-android-x86-7.1.1|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-x86-7.1.1.svg)](https://microbadger.com/images/butomo1989/docker-android-x86-7.1.1 "Get your own image badge on microbadger.com")|
|Linux|8.0|26|chrome|58.0|2.31|butomo1989/docker-android-x86-8.0|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-x86-8.0.svg)](https://microbadger.com/images/butomo1989/docker-android-x86-8.0 "Get your own image badge on microbadger.com")|
|Linux|8.1|27|chrome|61.0|2.33|butomo1989/docker-android-x86-8.1|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-x86-8.1.svg)](https://microbadger.com/images/butomo1989/docker-android-x86-8.1 "Get your own image badge on microbadger.com")|
|All |-|-|-|-|-|butomo1989/docker-android-real-device|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-real-device.svg)](https://microbadger.com/images/butomo1989/docker-android-real-device "Get your own image badge on microbadger.com")|
|Linux|All|All|All|All|All|butomo1989/docker-android-genymotion|[![](https://images.microbadger.com/badges/image/butomo1989/docker-android-genymotion.svg)](https://microbadger.com/images/butomo1989/docker-android-genymotion "Get your own image badge on microbadger.com")|

List of Devices
---------------

Type   | Device Name
-----  | -----
Phone  | Samsung Galaxy S6
Phone  | Nexus 4
Phone  | Nexus 5
Phone  | Nexus One
Phone  | Nexus S
Tablet | Nexus 7

Requirements
------------

Docker is installed in your system.

Quick Start
-----------

1. Run Docker-Android

	- For ***Linux OS***, please use image name that contains "x86"

		```bash
		docker run --privileged -d -p 6080:6080 -p 5554:5554 -p 5555:5555 -e DEVICE="Samsung Galaxy S6" --name android-container butomo1989/docker-android-x86-8.1
		```

	- For ***OSX*** and ***Windows OS***, please use Virtual Machine that support Virtualization with Ubuntu OS


2. Verify the ip address of docker host.

   - For OSX, you can find out by using following command:

     ```bash
     docker-machine ip default
     ```

   - For different OS, localhost should work.

3. Open ***http://docker-host-ip-address:6080*** from web browser.

Custom configurations
---------------------

[This document](README_CUSTOM_CONFIG.md) contains custom configurations of Docker-Android that you might need, e.g. Proxy, Changing language on fly, etc. 

Build Android project
---------------------

Docker-Android can be used for building Android project and executing its unit test. This following steps will illustrate how to build Android project:

1. Clone [this sample test project](https://github.com/googlesamples/android-testing).

    ```bash
    git clone git@github.com:googlesamples/android-testing.git
    ```

2. Build the project

    ```bash
    docker run -it --rm -v $PWD/android-testing/ui/espresso/BasicSample:/root/tmp butomo1989/docker-android-x86-8.1 tmp/gradlew build
    ```

Appium and Selenium Grid
------------------------

If you want to use Appium and Selenium Grid, you can follow [this document](README_APPIUM_AND_SELENIUM.md). It also contains sample and use cases.

Control android emulator outside container
------------------------------------------

```bash
adb connect <docker-machine-ip-address>:5555
```

![][adb_connection]

**Note:** You need to have Android Debug Bridge (adb) installed in your host machine.

SMS Simulation
--------------

1. Using telnet
	- Find the auth_token and copy it.

	 ```bash
	 docker exec -it android-container cat /root/.emulator_console_auth_token
	 ```

	- Access emulator using telnet and login with auth_token

	 ```bash
	 telnet <docker-machine-ip-address> 5554
	 ```

	- Login with given auth_token from 1.step

	 ```bash
	 auth <auth_token>
	 ```

	- Send the sms

	 ```bash
	 sms send <phone_number> <message>
	 ```

2. Using adb

	 ```bash
	 docker exec -it android-container adb emu sms send <phone_number> <message>
	 ```

3. You can also integrate it inside project using adb library.

![][sms]

Google Play Services and Google Play Store
------------------------------------------

Docker-Android contains Google Play Service (v12.8.74) and Google Play Store (v11.0.50). Both applications are downloaded from [apklinker](https://www.apklinker.com/), so please be aware of it in case you use private/company account to that applications.

VMWARE
------

This [document](README_VMWARE.md) shows you how to configure Virtual Machine on VMWARE to be able to run Docker-Android.

Cloud
-----

This [document](README_CLOUD.md) contains information about deploying Docker-Android on cloud services.

Genymotion
----------

![Genymotion](images/logo_genymotion.png)

For you who do not have ressources to maintain the simulator or to buy machines or need different device profiles, you need to give a try to [Genymotion Cloud](https://www.genymotion.com/cloud/). Docker-Android is integrated with Genymotion on different cloud services, e.g. Genymotion Cloud, AWS, GCP, Alibaba Cloud. Please follow [this document](README_GENYMOTION.md) for more detail.

Troubleshooting
---------------
All logs inside container are stored under folder **/var/log/supervisor**. you can print out log file by using **docker exec**. Example:

```bash
docker exec -it android-container tail -f /var/log/supervisor/docker-android.stdout.log
```

Special Thanks
--------------
- [Gian Christanto] for creating a great logo!

[appium]: <https://appium.io>
[espresso]: <https://google.github.io/android-testing-support-library/docs/espresso/>
[robotium]: <https://github.com/RobotiumTech/robotium>
[emulator samsung]: <images/emulator_samsung_galaxy_s6.png>
[emulator nexus]: <images/emulator_nexus_5.png>
[real device]: <images/real_device.png>
[adb_connection]: <images/adb_connection.png>
[sms]: <images/SMS.png>
[gian christanto]: <https://www.linkedin.com/in/gian-christanto-0b398b131/>
