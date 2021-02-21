
<!-- PROJECT LOGO -->
<br />
<p align="center">
  <h3 align="center">RTCF</h3>

  <p align="center">
    RTCF allows a usage of Orocos Realtime Components with (nearly) all the benefits you know from ROS.
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

Here's a blank template to get started:

<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
On development RTCF was tested on the following system. Other configuration might still work.

* Ros Melodic
* Ubuntu 18.04
* RTPreempt Realtime Patch

### Installation

1. install orocos
```sh
    export OROCOS_TARGET=gnulinux
    mkdir -p ~/ws/underlay_isolated/src/orocos
    cd ~/ws/underlay_isolated
    git clone --recursive https://github.com/orocos-toolchain/orocos_toolchain.git src/orocos/orocos_toolchain
    catkin_make_isolated --install
    source install_isolated/setup.sh
```
2. install rtt_ros_integration
  ```sh
    mkdir -p ~/ws/underlay/src
    cd ~/ws/underlay
    git clone https://github.com/orocos/rtt_ros_integration.git src/rtt_ros_integration
    catkin_make
    source devel/setup.sh
  ```
3. install RTCF
```sh
    mkdir -p ~/ws/src
    cd ~/ws
    git clone https://github.com/KIT-ISAS/RTCF src/RTCF
    catkin_make
    source devel/setup.sh
```
Add the source commands to your .bashrc or other comparable file in the same order
if you want the framework to stay enabled. 

#### Run Tests

To check if your installation works run in the RTCF workspace:
``` sh
cd ~/ws
catkin_make run_tests
```

<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

#### Simple Orocos Node

A empty orocos Node can be created with:

``` sh
orocreate-catkin-pkg my_node component
```


#### Create Orocos Messages from ROS Messages

From: [Source][https://github.com/orocos/rtt_ros_integration/tree/toolchain-2.9/rtt_roscomm#making-a-packages-ros-msg-and-srv-types-available]

```sh
rosrun rtt_roscomm create_rtt_msgs my_msgs
```

This should create a package with a CMakeLists.txt and the following content:

```
project(rtt_my_msgs)
find_package(catkin REQUIRED COMPONENTS rtt_roscomm)

# Generate typekits for ros .msg files
ros_generate_rtt_typekit(my_msgs)
# Generate the plugin which makes the services in my_msgs available
ros_generate_rtt_service_proxies(my_msgs)

# Call orocos_generate_package() after the above to export the proper targets
orocos_generate_package(
  DEPENDS my_msgs
  DEPENDS_TARGETS rtt_roscomm
)
```

#### More examples

More examples are in the rtcf_example folder.

<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
6. 

Also feel free to open an issue at any time. Everything i dont know i cant fix :)


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.


<!-- CONTACT -->
## Contact

Caplett - git@caplett.com

Project Link: [https://github.com/KIT-ISAS/RTCF](https://github.com/KIT-ISAS/RTCF)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

* Readme Template: [https://github.com/othneildrew/Best-README-Template](https://github.com/othneildrew/Best-README-Template)


