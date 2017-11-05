Create Activity
===============


Open ``Project View`` by clicking the dropdown at the top of the Project window and selecting ``Project``.

.. raw:: html
  <a href="../../_images/getting_started/python_activity/03_create_activity/01_open_project_view.png" target="_blank"><img src="../../_images/getting_started/python_activity/03_create_activity/01_open_project_view.png"></a>

---------------------------------------------------------------------------------------------------

Navigate to ``PythonActivity/app/src/main/java/demo.chaquopy.pythonactivity`` & delete ``MainActivity.java``.

Uncheck ``Safe delete`` in the following dialog.

.. raw:: html
  <a href="../../_images/getting_started/python_activity/03_create_activity/02_delete_java_main_activity.png" target="_blank"><img src="../../_images/getting_started/python_activity/03_create_activity/02_delete_java_main_activity.png"></a>

.. raw:: html
  <a href="../../_images/getting_started/python_activity/03_create_activity/03_uncheck_safe_delete.png" target="_blank"><img src="../../_images/getting_started/python_activity/03_create_activity/03_uncheck_safe_delete.png"></a>

---------------------------------------------------------------------------------------------------

Next, we'll create some directories & files that are required for our Python activity.


.. raw:: html
  <a href="../../_images/getting_started/python_activity/03_create_activity/04_create_directory.png" target="_blank"><img src="../../_images/getting_started/python_activity/03_create_activity/04_create_directory.png"></a>

.. raw:: html
  <a href="../../_images/getting_started/python_activity/03_create_activity/05_create_python_file.png" target="_blank"><img src="../../_images/getting_started/python_activity/03_create_activity/05_create_python_file.png"></a>

---------------------------------------------------------------------------------------------------

Create all of the following directories & files:

Directories:
  - ``PythonActivity/app/src/main/python``
  - ``PythonActivity/app/src/main/python/demo``
  - ``PythonActivity/app/src/main/python/demo/chaquopy``
  - ``PythonActivity/app/src/main/python/demo/chaquopy/pythonactivity``

Files:
  - ``PythonActivity/app/src/main/python/__init__.py``
  - ``PythonActivity/app/src/main/python/demo/__init__.py``
  - ``PythonActivity/app/src/main/python/demo/chaquopy/__init__.py``
  - ``PythonActivity/app/src/main/python/demo/chaquopy/pythonactivity/__init__.py``
  - ``PythonActivity/app/src/main/python/demo/chaquopy/pythonactivity/main_activity.py``

.. raw:: html
  <a href="../../_images/getting_started/python_activity/03_create_activity/06_file_structure.png" target="_blank"><img src="../../_images/getting_started/python_activity/03_create_activity/06_file_structure.png"></a>

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/src/main/python/demo/chaquopy/pythonactivity/main_activity.py`` and add the following code:

.. code-block:: python

  from demo.chaquopy.pythonactivity import R

  from java import static_proxy, Override, jvoid

  from android.os             import Bundle
  from android.support.v7.app import AppCompatActivity


  # Python activities require a static_proxy implementation
  #   in order to generate a Java source file from their contents.
  class MainActivity(static_proxy(AppCompatActivity)):

    # Any methods that will be accessed from Java must implement
    #   @Override(java_return_type, [method_args])
    @Override(jvoid, [Bundle])
    def onCreate(self, state):
      AppCompatActivity.onCreate(self, state)
      self.setContentView(R.layout.activity_main)
