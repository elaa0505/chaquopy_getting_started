Update Configuration
====================

Now that our activity is set up, we have to make some adjustments to various configuration files.

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/build.gradle`` and add the following code:

@ buildscript.repositories:

.. code-block:: guess

  maven{url "https://chaquo.com/maven"}

@ buildscript.dependencies:

.. code-block:: guess

  classpath "com.chaquo.python:gradle:0.5.0"

.. raw:: html
  <a href="../../_images/getting_started/python_activity/04_update_configuration/01_primary_gradle.png" target="_blank"><img src="../../_images/getting_started/python_activity/04_update_configuration/01_primary_gradle.png"></a>

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/build.gradle`` and add the following code:

@ root:

.. code-block:: guess

  apply plugin: "com.chaquo.python"  // Must come after com.android.application

@ android.defaultConfig:

.. code-block:: guess

  ndk {abiFilters "x86", "armeabi-v7a"}
  python {
    buildPython "C:/path/to/your/python.exe"
    version "2.7.10"
    staticProxy "demo.chaquopy.pythonactivity.main_activity"
  }

.. raw:: html
  <a href="../../_images/getting_started/python_activity/04_update_configuration/02_module_gradle.png" target="_blank"><img src="../../_images/getting_started/python_activity/04_update_configuration/02_module_gradle.png"></a>

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/src/main/AndroidManifest.xml`` and add the following code:

@ manifest.application:

.. code-block:: guess

  android:name = "com.chaquo.python.android.PyApplication"

update manifest.application.activity.name:

.. code-block:: guess

  ".main_activity.MainActivity"

.. raw:: html
  <a href="../../_images/getting_started/python_activity/04_update_configuration/03_manifest.png" target="_blank"><img src="../../_images/getting_started/python_activity/04_update_configuration/03_manifest.png"></a>

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/src/main/res/layout/activity_main.xml`` and update the ``tools:context`` attribute of the primary layout:

.. code-block:: guess

  "demo.chaquopy.pythonactivity.main_activity.MainActivity"

.. raw:: html
  <a href="../../_images/getting_started/python_activity/04_update_configuration/04_layout.png" target="_blank"><img src="../../_images/getting_started/python_activity/04_update_configuration/04_layout.png"></a>

