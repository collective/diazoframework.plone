Introduction
============
This package is the base for creating CSS frameworks (e.g. Twitter
Bootstrap, Zurb Foundation, etc.) to be used with Diazo. They are 
useful for creating themes based on CSS frameworks. A Diazo framework 
should provide the framework resources and diazo rules to reuse and 
add to in a Diazo theme.

How to setup a Diazo Framework
------------------------------
A framework package is set up as follows:

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

This is not your typical framework package
------------------------------------------
This package is the parent of all frameworks and provides rules
and resources that are practical to use in other frameworks as
well as themes. 

**resources**

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
      _ content.xml
      _ contenttodecocells.xml (only to be used with the body layout of ../sunburst/index.html)  
      
      
    _ sunburst
      Provides the resources from *plonetheme.sunburst*.
      
    _ index.html
      An empty html file to fill. It contains a 
      `<html>`, `<head>`, `<title>` and `<body>`,
      nothing more.

Examples of typical frameworks and themes
-----------------------------------------
For a typical diazoframework check [diazoframework.amazium](https://github.com/TH-code/diazoframework.amazium),
with typical diazotheme [diazotheme.amazium](https://github.com/TH-code/diazotheme.amazium)

A theme that leans towards the complex is 
[diazoframework.bootstrap](https://github.com/TH-code/diazoframework.bootstrap) 
with 
[diazotheme.bootstrap](https://github.com/TH-code/diazotheme.bootstrap). 
You can then see the power of childthemes at work in 
[diazotheme.bootswatch](https://github.com/TH-code/diazotheme.bootswatch).

### Current frameworks

- [diazoframework.amazium](https://github.com/TH-code/diazoframework.amazium)
- [diazoframework.baseline](https://github.com/TH-code/diazoframework.baseline)
- [diazoframework.bootstrap](https://github.com/TH-code/diazoframework.bootstrap)
- [diazoframework.foundation](https://github.com/TH-code/diazoframework.foundation)
- [diazoframework.goldilocks](https://github.com/TH-code/diazoframework.goldilocks)
- [diazoframework.kube](https://github.com/TH-code/diazoframework.kube)
- [diazoframework.purecss](https://github.com/TH-code/diazoframework.purecss)
- [diazoframework.skeleton](https://github.com/TH-code/diazoframework.skeleton)

### Current themes

- [diazotheme.amazium](https://github.com/TH-code/diazotheme.amazium)
- [diazotheme.baseline](https://github.com/TH-code/diazotheme.baseline)
- [diazotheme.bootstrap](https://github.com/TH-code/diazotheme.bootstrap)
- [diazotheme.bootswatch](https://github.com/TH-code/diazotheme.bootswatch)
- [diazotheme.foundation](https://github.com/TH-code/diazotheme.foundation)
- [diazotheme.goldilocks](https://github.com/TH-code/diazotheme.goldilocks)
- [diazotheme.kube](https://github.com/TH-code/diazotheme.kube)
- [diazotheme.plone](https://github.com/TH-code/diazotheme.plone)
- [diazotheme.purecss](https://github.com/TH-code/diazotheme.purecss)
- [diazotheme.skeleton](https://github.com/TH-code/diazotheme.skeleton)
