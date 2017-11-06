Test App
========

The app is ready to run, start it by clicking the green ``play`` button in the toolbar.

.. image:: /_images/getting_started--python_activity--05_test_app--01_run_app.png
	:target: /_images/getting_started--python_activity--05_test_app--01_run_app.png

.. image:: /_images/getting_started--python_activity--05_test_app--02_app.png
	:target: /_images/getting_started--python_activity--05_test_app--02_app.png

---------------------------------------------------------------------------------------------------

Now that the app is up & running, we can interact with the layout from the activity.

Open ``PythonActivity/app/src/main/res/layout/activity_main.xml`` and add the following code:

@ TextView:

.. code-block:: guess

	android:id = "@+id/label"

.. image:: /_images/getting_started--python_activity--05_test_app--03_layout.png
	:target: /_images/getting_started--python_activity--05_test_app--03_layout.png

---------------------------------------------------------------------------------------------------

Open ``PythonActivity/app/src/main/python/demo/chaquopy/pythonactivity/main_activity.py`` and add the following code:

@ MainActivity.onCreate:

.. code-block:: guess

	label = self.findViewById(R.id.label)
	label.setText("Python Activity Loaded!")

.. image:: /_images/getting_started--python_activity--05_test_app--04_activity.png
	:target: /_images/getting_started--python_activity--05_test_app--04_activity.png

---------------------------------------------------------------------------------------------------

Now when we run the app again, the label is updated by the activity:

.. image:: /_images/getting_started--python_activity--05_test_app--05_app.png
	:target: /_images/getting_started--python_activity--05_test_app--05_app.png
