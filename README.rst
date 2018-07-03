====================
diazoframework.plone
====================


Introduction
============

``diazoframework.plone`` package is the base for creating CSS frameworks 
(e.g. Twitter Bootstrap, Zurb Foundation, etc.) using the **theming** and 
**packaging** features available for create Diazo_ theme using `plone.app.theming`_. 

They are useful for creating themes based on CSS frameworks. A Diazo framework 
should provide the framework resources and diazo rules to reuse and add to in 
a Diazo theme.


How to setup a Diazo Framework
------------------------------

A framework package is set up as follows:

::

    _ diazoframework.name
      I tend to use paster to create the package scaffolding.
      
      _ diazoframework
        _ name
          _ framework  
            This folder is registered through configure.zcml
            as the framework and will be traversable through 
            /++framework++name.
              
            _ resources  
              The resources are the files you get in the framework
              zip you download. In my opinion it is best to change
              as little as possible for future upgrading of 
              the files. All changes you make here you will also 
              have to make in future versions of the framework.
              
            _ rules
              CSS frameworks generally work by delivering styles
              and functionality for specific html structures.  
              The rules folder contains diazo rule snippets, that 
              mold the plone html into blocks the framework 
              expects. These rules are often a little more complex
              than the regular put my content div in that theme div
              and remold the html in a generic way.  
              The rules files can be included through XIncludes 
              into a diazotheme.
               
            _ preview.png
              I like to provide a generic thumbnail for the theme
              panel.
                
        _ __init__.py
        _ configure.zcml
        _ version.txt
      _ __init__.py
    _ docs
      _ HISTORY.txt
      _ INSTALL.txt
      _ LICENSE.GPL
      _ LICENSE.txt
      
    _ MANIFEST.in 
    _ README.md 
    _ setup.py


Requirements
============

- From the Plone 4.1.x To the Plone 4.3 latest version (https://plone.org/download)
- The ``plone.app.theming`` package (*You will need enable it to use this package*)


Features
========

- Provides the *plonetheme.classic* resources.
- Provides the *plonetheme.sunburst* resources.
- Provides the *Respond.js v1.1.0* CSS/JS resources.
- Provides the 12-column Deco Grid System CSS resource.
- Provides the 16-column Deco Grid System CSS resource.
- Included Diazo rules for the ``head``, ``icon``, ``logo``, ``utility`` and ``content`` CSS styles.


Installation
============


Buildout
--------

If you are a developer, you might enjoy installing it via buildout.

For install ``diazoframework.plone`` package add it to your ``buildout`` section's 
*eggs* parameter e.g.: ::

   [buildout]
    ...
    eggs =
        ...
        diazoframework.plone


and then running ``bin/buildout``.

Or, you can add it as a dependency on your own product ``setup.py`` file: ::

    install_requires=[
        ...
        'diazoframework.plone',
    ],


Resources
=========

The resources of this framework can be reached through 
``/++framework++plone`` and there are placed at 
``diazoframework.plone/diazoframework/plone/framework/`` 
directory with following resources files:


This is not your typical framework package
------------------------------------------

This package is the parent of all frameworks and provides rules
and resources that are practical to use in other frameworks as
well as themes

::

    _ classic
      Provides the resources from *plonetheme.classic*.
      
    _ css
      _ decogrids-12.css
      _ decogrids-16.css
      _ respond.css
      
    _ favicon
    _ img
      Plone icons and logo's to restructure *portal-logo*.
      
    _ js
      _ respond.min.js
      
    _ rules
      _ head
        _ base.xml
        _ css.xml
        _ icons.xml
        _ ie-classes.xml
        _ js.xml
        
      _ icon
        _ black-128.xml
        _ black-192.xml
        _ black-256.xml
        _ black-32.xml
        _ black-40.xml
        _ black-48.xml
        _ black-56.xml
        _ black-64.xml
        _ blue-128.xml
        _ blue-192.xml
        _ blue-256.xml
        _ blue-32.xml
        _ blue-40.xml
        _ blue-48.xml
        _ blue-56.xml
        _ blue-64.xml
        _ default-128.xml
        _ default-192.xml
        _ default-256.xml
        _ default-32.xml
        _ default-40.xml
        _ default-48.xml
        _ default-56.xml
        _ default-64.xml
        _ white-128.xml
        _ white-192.xml
        _ white-256.xml
        _ white-32.xml
        _ white-40.xml
        _ white-48.xml
        _ white-56.xml
        _ white-64.xml
        
      _ logo
        _ black-128.xml
        _ black-192.xml
        _ black-256.xml
        _ black-32.xml
        _ black-40.xml
        _ black-48.xml
        _ black-56.xml
        _ black-64.xml
        _ blue-128.xml
        _ blue-192.xml
        _ blue-256.xml
        _ blue-32.xml
        _ blue-40.xml
        _ blue-48.xml
        _ blue-56.xml
        _ blue-64.xml
        _ default-128.xml
        _ default-192.xml
        _ default-256.xml
        _ default-32.xml
        _ default-40.xml
        _ default-48.xml
        _ default-56.xml
        _ default-64.xml
        _ white-128.xml
        _ white-192.xml
        _ white-256.xml
        _ white-32.xml
        _ white-40.xml
        _ white-48.xml
        _ white-56.xml
        _ white-64.xml
        
      _ utility
        _ clean.xml
        _ responsify.xml
        _ structures.xml
        _ toolbar.xml
      
    _ sunburst
      Provides the resources from *plonetheme.sunburst*.
      
    _ index.html
      An empty html file to fill. It contains a 
      `<html>`, `<head>`, `<title>` and `<body>`,
      nothing more.


Typical frameworks and themes examples
======================================

For a typical diazoframework check `diazoframework.amazium <https://github.com/TH-code/diazoframework.amazium>`_,
with typical diazotheme `diazotheme.amazium <https://github.com/TH-code/diazotheme.amazium>`_

A theme that leans towards the complex is 
`diazoframework.bootstrap <https://github.com/TH-code/diazoframework.bootstrap>`_ 
with 
`diazotheme.bootstrap <https://github.com/TH-code/diazotheme.bootstrap>`_. 
You can then see the power of childthemes at work in 
`diazotheme.bootswatch <https://github.com/TH-code/diazotheme.bootswatch>`_.

Current frameworks
------------------

- `diazoframework.amazium <https://github.com/TH-code/diazoframework.amazium>`_
- `diazoframework.baseline <https://github.com/TH-code/diazoframework.baseline>`_
- `diazoframework.bootstrap <https://github.com/TH-code/diazoframework.bootstrap>`_
- `diazoframework.foundation <https://github.com/TH-code/diazoframework.foundation>`_
- `diazoframework.goldilocks <https://github.com/TH-code/diazoframework.goldilocks>`_
- `diazoframework.kube <https://github.com/TH-code/diazoframework.kube>`_
- `diazoframework.purecss <https://github.com/TH-code/diazoframework.purecss>`_
- `diazoframework.skeleton <https://github.com/TH-code/diazoframework.skeleton>`_

Current themes
--------------

- `diazotheme.amazium <https://github.com/TH-code/diazotheme.amazium>`_
- `diazotheme.baseline <https://github.com/TH-code/diazotheme.baseline>`_
- `diazotheme.bootstrap <https://github.com/TH-code/diazotheme.bootstrap>`_
- `diazotheme.bootswatch <https://github.com/TH-code/diazotheme.bootswatch>`_
- `diazotheme.foundation <https://github.com/TH-code/diazotheme.foundation>`_
- `diazotheme.goldilocks <https://github.com/TH-code/diazotheme.goldilocks>`_
- `diazotheme.kube <https://github.com/TH-code/diazotheme.kube>`_
- `diazotheme.plone <https://github.com/TH-code/diazotheme.plone>`_
- `diazotheme.purecss <https://github.com/TH-code/diazotheme.purecss>`_
- `diazotheme.skeleton <https://github.com/TH-code/diazotheme.skeleton>`_


Contribute
==========

- Issue Tracker: https://github.com/TH-code/diazoframework.plone/issues
- Source Code: https://github.com/TH-code/diazoframework.plone


License
=======

The project is licensed under the GPLv2.


Credits
-------

- Thijs Jonkman (t.jonkman at gmail dot com).


Amazing contributions
---------------------

- Leonardo J. Caballero G. aka macagua (leonardocaballero at gmail dot com).

You can find an updated list of package contributors on https://github.com/TH-code/diazoframework.plone/contributors

.. _`diazoframework.plone`: https://github.com/TH-code/diazoframework.plone#current-frameworks
.. _`Diazo`: http://diazo.org
.. _`plone.app.theming`: https://pypi.org/project/plone.app.theming/
