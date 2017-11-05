Update Configuration
====================

Now that our activity is set up, we have to make some adjustments to various configuration files.

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/build.gradle`` and add the following code:

@ buildscript.repositories:

.. code-block:: java
  maven{url "https://chaquo.com/maven"}

@ buildscript.dependencies:

.. code-block:: java
  classpath "com.chaquo.python:gradle:0.5.0"

.. image:: /_images/python_activity/04_update_configuration/01_primary_gradle.png

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/build.gradle`` and add the following code:

@ root:

.. code-block:: java
  apply plugin: "com.chaquo.python"  // Must come after com.android.application

@ android.defaultConfig:

.. code-block:: java
  ndk {abiFilters "x86", "armeabi-v7a"}
  python {
    buildPython "C:/path/to/your/python.exe"
    version "2.7.10"
    staticProxy "demo.chaquopy.pythonactivity.main_activity"
  }

.. image:: /_images/python_activity/04_update_configuration/02_module_gradle.png

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/src/main/AndroidManifest.xml`` and add the following code:

@ manifest.application:

.. code-block:: xml
  android:name = "com.chaquo.python.android.PyApplication"

update manifest.application.activity.name:

.. code-block:: xml
  ".main_activity.MainActivity"

.. image:: /_images/python_activity/04_update_configuration/03_manifest.png

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/src/main/res/layout/activity_main.xml`` and add the following code:

update the ``tools:context`` attribute of the primary layout:

.. code-block:: xml
  "demo.chaquopy.pythonactivity.main_activity.MainActivity"

.. image:: /_images/python_activity/04_update_configuration/04_layout.png

