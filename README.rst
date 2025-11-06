=======================================
Mobile Test Automation
=======================================

A robust automation framework built using **Robot Framework** and **Appium** to test native Android applications. This project showcases structured test design (Page Object Model adaptation), external data handling, and custom library creation, including a basic **Visual State Check** for enhanced stability.

------------

Prerequisites
------------

Ensure the following tools are installed and configured on your system before proceeding.

1. Development Environment
*************************

* **Java Development Kit (JDK):** Required for Android tools.
* **Android Studio:** Required for the Android SDK, platform tools (ADB), and AVD Manager.
* **Node.js & npm:** Required for installing and running Appium Server.
* **Python 3.10+:** Required for Robot Framework and custom libraries.

2. Automation Tools
*******************

* **Appium Server (v2.x recommended):**
    
    .. code-block:: bash

        npm install -g appium@next

* **Appium Drivers (UIAutomator2):**
    
    .. code-block:: bash

        appium driver install uiautomator2

------------

Project Setup
------------

Follow these steps to configure the project environment and dependencies.

1. Clone the Repository
***********************

.. code-block:: bash

    git clone [Your Repository URL]
    cd SDET-Mobile-Automation

2. Create and Activate Python Virtual Environment
************************************************

.. code-block:: bash

    python3 -m venv venv
    source venv/bin/activate  # macOS/Linux
    # .\venv\Scripts\activate # Windows (PowerShell)

3. Install Dependencies
***********************

Install all required Python libraries, including Robot Framework, AppiumLibrary, and the ``opencv-python`` library used for custom visual validation.

.. code-block:: bash

    pip install -r requirements.txt

4. Configure Capabilities
*************************

The project relies on variables defined in :file:`resources/TestVariables.py`. **You MUST update the following two variables** to match your local setup:

* **APP_PATH:** Absolute path to the **``ApiDemos-debug.apk``** file.
* **PLATFORM\_VERSION:** The **exact OS version** (e.g., ``13``) of your running emulator/device.

------------

Emulator / Device Setup
------------

1. Start Appium Server
***********************

Start the Appium server in a dedicated terminal window.

.. code-block:: bash

    appium

2. Launch Emulator
******************

Launch an Android Virtual Device (AVD) using Android Studio's AVD Manager. Ensure the device is running **before** executing tests.

------------

Execution
------------

Tests should be run from the project root directory (:file:`SDET-Mobile-Automation/`).

Run All Tests
****************

.. code-block:: bash

    robot tests/