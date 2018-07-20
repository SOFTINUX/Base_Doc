Configure Rider
****************

.. note::

   This page is for Rider 2018.2 and upper.

| Rider doesn't use all .sln tag to build your application.
| In this page, we show to configure Rider to build bundles before build the application.

Create an external tool
=======================

Click on edit configuration

.. image:: ../_static/images/screen1.png
   :alt: open configuration

If you have already one configuration, click on it

.. image:: ../_static/images/screen2.png
   :alt: configuration editor

| And click the plus sign in section Before launch (number 2 on picture).
| In popup menu, select external tool

.. image:: ../_static/images/screen3.png

In new window click on plus sign:

.. image:: ../_static/images/screen4.png

Now, in external tool configuration window:

1. enter a name for your new external tool configuration.
2. in program field, enter same text as screen shot.
3. in arguments field enter bundles.
4. working directory is auto completed.
5. click on save.

.. image:: ../_static/images/screen5.png