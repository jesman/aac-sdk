# Alexa Auto SDK

Alexa Auto SDK contains essential client-side software required to integrate Alexa into the automobile. The Alexa Auto SDK provides a runtime engine for communicating with the Alexa service. It also provides interfaces that allow the developer to implement platform specific behavior such as audio input, media playback, template and state rendering, and phone control. It also includes a sample app that demonstrates how to use the Alexa Auto SDK interfaces.

**Table of Contents**:

* [What is Included](#whatsincluded)
* [General Build Requirements](#generalbuildreqs)
* [Vehicle Configuration Information](#vehicleconfigurationdatarequirements)
* [Build the Alexa Auto SDK](#buildthesdk)
* [Alexa Auto SDK Architecture](#architecture)
* [Release Notes and Known Issues](#relnotesknownissues)

> **Tip**: Try looking at [Need Help?](./NEED_HELP.md) if you don't see the topic you are looking for.

## What is Included<a id="whatsincluded"></a>

The following components are included with the Alexa Auto SDK:

* [Builder](./builder/README.md): This directory contains the scripts that allow developers to build modules for a variety of hardware targets.

* [Modules](./modules): This directory contains the Alexa Auto SDK interfaces and source code.

* [Android Sample App](./samples/android/README.md): This directory contains the Android sample application that uses the Alexa Auto SDK to demonstrate end-to-end functionality.

    * > **Important!** You need an [Amazon Developer Account](https://developer.amazon.com/home.html) to use the Alexa Auto SDK. Read the [Sample App](./samples/android/README.md) documentation for more details.

Alexa Auto SDK API Reference documentation is available for Android and C++. Go to the appropriate directory and open the **`index.html`** file with a web browser.

Access the Alexa Auto SDK API reference documentation from the links below.

* [Alexa Auto SDK for Android](./docs/android/)
* [Alexa Auto SDK for C++](./docs/cpp/)

## General Build Requirements<a id="generalbuildreqs"></a>

You can build on a Linux, Unix, or macOS host of your choice.

However, we recommend and support running a Docker environment with the following configuration.

* macOS Sierra or Ubuntu 16.04 LTS
* Processor: 2.5 GHz
* Memory: 16 Gb
* Storage: 1 Gb+ available to use.

## Vehicle Configuration Information<a id="vehicleconfigurationdatarequirements"></a>

The Vehicle Configuration class provides an interface for vehicle information to be supplied to the SDK. This information is required to pass the certification process.

Read detailed information about the vehicle configuration class in the API reference documentation.

* [Alexa Auto SDK for Android](./docs/android/)
* [Alexa Auto SDK for C++](./docs/cpp/)

## Build the Alexa Auto SDK<a id="buildthesdk"></a>

To build the Alexa Auto SDK you should read and understand the instructions in the [Builder README](./builder/README.md).

The recommended and tested Linux hosts are **Ubuntu 16.04 LTS** or **macOS Sierra**.

### Supported Target Platforms

Alexa Auto SDK is supported on the following platforms:

* Android ARM 32-bit
* Android ARM 64-bit (using 32-bit build)
* Android x86
* QNX ARM 64-bit

> **Note**: For Android targets, Alexa Auto SDK is available as a prebuilt library on GitHub. Read the instructions about accessing and using the library in the [samples/android/ directory](./samples/android/README.md).

## Alexa Auto SDK Architecture<a id="architecture"></a> Overview

The Alexa Auto SDK is designed to allow flexibility in the integration of Alexa as a part of the Auto in-cabin experience. The Alexa Auto SDK Engine provides runtime support for Alexa and other services and allows the application to integrate with platform specific functionality. Platform specific behavior in Alexa Auto is abstracted into interfaces called "Platform Interfaces." These interfaces should be extended in the application and registered with the Engine.

The Platform Interfaces are documented in their respective module's API documentation.

> **Note**: This diagram shows only some of the available platform interfaces.

![architecture](./assets/aac_architecture.png)

### ![Alexa Auto SDK Engine](./assets/number-1.png) Alexa Auto SDK Engine

The runtime implementation of the Alexa Auto SDK is known as the Engine. Modules extend the Engine by providing services and defining the runtime behavior for Platform Interfaces that are registered by application. The application software communicates with the Engine through the API defined by the Platform Interfaces.

Click [here](./builder/README.md) for more information.

### ![Alexa Auto SDK Engine](./assets/number-2.png) Core Module

The Core Module includes Platform Interfaces and runtime Engine support for Core features in the Alexa Auto SDK, such as logging, location, and network information. The services are used by components in other modules and are required by Alexa Auto SDK.

Click [here](./modules/core/README.md) for more information.

### ![Alexa Auto SDK Engine](./assets/number-3.png) Alexa Module

The Alexa Module includes Platform Interfaces and runtime Engine support for Alexa features in the Alexa Auto SDK. View some [sequence diagrams](./SEQUENCE_DIAGRAMS.md) for more details.

This module includes support for audio input, media playback, template and state rendering, and much more.

Click [here](./modules/alexa/README.md) for more information.

### ![Alexa Auto SDK Engine](./assets/number-4.png) Navigation Module

The Navigation Module includes Platform Interfaces and runtime Engine support for Alexa to interface with the onboard navigation system.

Click [here](./modules/navigation/README.md) for more information.

### ![Alexa Auto SDK Engine](./assets/number-5.png) Phone Control Module

The Phone Control Module includes Platform Interfaces and runtime Engine support for Alexa to interface with the onboard telephony system.

Click [here](./modules/phone-control/README.md) for more information.

## Getting Started With the Android Sample App

The Android Sample App provides an example of how to use the Alexa Auto SDK. The [Android Sample App README](./samples/android/README.md) has detailed instructions about how to use the sample app.

## Release Notes and Known Issues<a id="relnotesknownissues"></a>

> **Note**: Feature enhancements, updates, and resolved issues from previous releases are available to view in [CHANGELOG.md](./CHANGELOG.md)

### v1.1.1 released on 2018-09-10:

#### Enhancements

This release is for bug fixes only. There are no new features or enhancements.

#### Resolved Issues

Issues fixed in this release:

* Update a dependency build recipe to skip the checksum verification to allow for document changes in the current tag.

#### Known Issues

There are no known issues in this release.

Sample App issues are documented in the [Sample App README](./samples/android/README.md#androidsampleapprelnote).
