YUI 3 Scaffolding
=================

A set of pre-packaged starter files for YUI module developers. The distinction is: 

* YUI module **users**: People who are wiring YUI modules into a web page: adding an 
  animation effect, rendering a canned widget. People who are writing small amounts 
  of glue code inside a ``YUI().use()``.
  
* YUI module **developers**: People who are building widgets and other chunks for 
  easy reuse. People who are writing most of their code inside ``YUI.add()``.

YUI Scaffolding is for the developers. The goal is to help bootstrap your
way to writing YUI modules *without* forcing you to mess around with the powerful, 
but also finicky and poorly documented YUI Builder.

Instead of going through a build/deploy cycle, the approach here is that you 
hand-author your own ``YUI.add()`` and ping pong back and forth between adding module 
code, writing tests, and refreshing the associated test runner HTML file. As your 
module matures, you can always migrate it over to YUI Builder. Or not.

Scaffold Modules
----------------

This project provides three flavors of scaffold modules for use in YUI projects. 
Each module is configured to run off the local filesystem, without assuming a web 
server or combo loader. In order of complexity:

example-basic
    A dead-simple example object with a single ``hello()`` method and a single
    working test.

example-component
    An example object derived from ``Y.Base``, with a single attribute, a single
    ``hello()`` method, and a single working test.

example-widget
    An example object derived from ``Y.Widget``, with a single attribute, a 
    minimal ``renderUI()``/``syncUI()`` implementation, and a single working test. 
    The widget also includes a CSS file delivered by setting ``skinnable: true``. 
    This is where some serious hackery ensues, since YUI skin conventions kind of
    assume you are using the builder and have deployed to a combo loader. This
    project is set up to make it easy to just noodle away on your widget's look and 
    feel. You can decide later on whether you want to build and load assets the way 
    the core YUI widgets do, or some other way.