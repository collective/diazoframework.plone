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

**diazoframework.name**  
I tend to use paster to create the package scaffolding.
- **diazoframework**
    - **name**
        - **framework**  
          This folder is registered through configure.zcml
          as the framework and will be traversable through 
          /++framework++name.
            - **resources**  
              The resources are the files you get in the framework
              zip you download. In my opinion it is best to change
              as little as possible for future upgrading of 
              the files. All changes you make here you will also 
              have to make in future versions of the framework.
            - **rules**  
              CSS frameworks generally work by delivering styles
              and functionality for specific html structures.  
              The rules folder contains diazo rule snippets, that 
              mold the plone html into blocks the framework 
              expects. These rules are often a little more complex
              than the regular put my content div in that theme div
              and remold the html in a generic way.  
              The rules files can be included through XIncludes 
              into a diazotheme.
            - **preview.png**  
              I like to provide a generic thumbnail for the theme
              panel.
        - **__init__.py**
        - **configure.zcml**
        - **version.txt**
    - **__init__.py**
- **docs**
    - **HISTORY.txt**
    - **INSTALL.txt**
    - **LICENSE.GPL**
    - **LICENSE.txt**
- **MANIFEST.in**
- **README.md**
- **setup.py**

This is not your typical framework package
------------------------------------------
This package is the parent of all frameworks and provides rules
and resources that are practical to use in other frameworks as
well as themes. It contains:

- **classic**  
  Provides the resources from *plonetheme.classic*.
- **css**
    - decogrids-12.css
    - decogrids-16.css
    - respond.css
- **favicon**
- **img**  
  Plone icons and logo's to restructure *portal-logo*.
- **js**
    - respond.min.js
- **rules**
    - **head**
    - **icon**
    - **logo**
    - **utility**
    - content.xml
- **sunburst**  
  Provides the resources from *plonetheme.sunburst*.
- **index.html**  
  An empty html file to fill. It contains a <html>, <head>, <title> 
  and <body>, nothing more

For a typical diazoframework check [diazoframework.amazium](https://github.com/TH-code/diazoframework.amazium)

Current frameworks
------------------
- [diazoframework.amazium](https://github.com/TH-code/diazoframework.amazium)
- [diazoframework.baseline](https://github.com/TH-code/diazoframework.baseline)
- [diazoframework.bootstrap](https://github.com/TH-code/diazoframework.bootstrap)
- [diazoframework.foundation](https://github.com/TH-code/diazoframework.foundation)
- [diazoframework.goldilocks](https://github.com/TH-code/diazoframework.goldilocks)
- [diazoframework.kube](https://github.com/TH-code/diazoframework.kube)
- [diazoframework.purecss](https://github.com/TH-code/diazoframework.purecss)
- [diazoframework.skeleton](https://github.com/TH-code/diazoframework.skeleton)

Current themes
--------------
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
