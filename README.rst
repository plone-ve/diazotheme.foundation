=====================
diazotheme.foundation
=====================


Introduction
============

``diazotheme.foundation`` package provides diazo themes based on the `Zurb Foundation CSS framework`_ 
using the **theming** and **packaging** features available for create `Diazo`_ theme
using `plone.app.theming`_.

``diazotheme.foundation`` package contains the following diazo implementations: 

- **Foundation Starter Theme**, is the Foundation Starter theme on diazo based.
- **Foundation Example Theme**, a diazo theme based for Zurb Foundation.


How to create a child theme
---------------------------

Any of the three theme folders can be used to create your own child theme, 
based on `diazoframework.foundation`_. You can either wrap the theme up in a package 
or you can create a zip file of the folder and upload that to the theme panel.

There are two ways of creating a child theme.


The package way
^^^^^^^^^^^^^^^

For this example, lets assume we are creating a package called
``diazotheme.newtheme`` and we will copy the ``starter`` theme in this 
package.

1. Created the ``diazotheme.newtheme`` package (for instance through ``paster`` script).

2. Copy ``diazotheme.foundation/diazotheme/foundation/starter`` to
   ``diazotheme.newtheme/diazotheme/newtheme/starter``.

3. Rename ``diazotheme.newtheme/diazotheme/newtheme/starter``
   to ``diazotheme.newtheme/diazotheme/newtheme/static`` (arbitrary
   name).

4. Add `<plone:static directory="static" name="newtheme" type="theme"/>`
   to ``diazotheme.newtheme/diazotheme/newtheme/configure.zcml``.

5. Change ``diazotheme.newtheme/diazotheme/newtheme/static/manifest.cfg``
   to reflect the changes, so: ::

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png


The zip file way
^^^^^^^^^^^^^^^^

Again, lets assume we use the ``theme`` theme and we want to end up
with the ``newtheme`` name.

1. Copy ``diazotheme.foundation/diazotheme/foundation/theme`` to your file system.

2. Rename ``theme`` to ``newtheme`` (the folder name will become the
   theme name in the theme panel)

3. Change ``newtheme/manifest.cfg``
   to reflect the changes, so: ::

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png

4. Customize your theme.

5. When you are finished customizing, create a zip archive of the 
   ``newtheme`` folder.

6. Upload the ``newtheme.zip`` in the plone theme panel.


Screenshots
===========

..
    Foundation Starter Theme
    ------------------------

    Layout of the site when viewed in a computer resolution:

    .. image:: https://github.com/TH-code/diazoframework.foundation/raw/master/diazoframework/foundation/framework/preview.png
      :alt: Foundation Starter Theme
      :align: center


Foundation Example Theme
------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/TH-code/diazotheme.foundation/raw/master/diazotheme/foundation/theme/preview.png
  :alt: Foundation Example Theme
  :align: center


Requirements
============

- From the Plone 4.1.x To the Plone 4.3 latest version (https://plone.org/download)
- The ``plone.app.theming`` package (*You will need enable it via "Add-ons" control 
  panel to use this package*)
- The ``diazoframework.foundation`` package (*You will need enable it via "buildout" 
  configuration to use this package*)


Features
========

- Provides the diazo rules for *Foundation Starter* theme.
- Provides the diazo rules for *Foundation Example* theme.


Installation
============


Buildout
--------

If you are a developer, you might enjoy installing it via buildout.

For install ``diazotheme.foundation`` package add it to your ``buildout`` section's 
*eggs* parameter e.g.: ::

   [buildout]
    ...
    eggs =
        ...
        diazotheme.foundation


and then running ``bin/buildout``.

Or, you can add it as a dependency on your own product ``setup.py`` file: ::

    install_requires=[
        ...
        'diazotheme.foundation',
    ],


Resources
=========

This package is the parent of all Plone diazo themes and 
provides rule that are practical to use in other diazo themes.


Foundation Starter Theme
------------------------

The resources of this theme can be reached through

    ``/++theme++foundation-starter``

There are placed at ``diazotheme.foundation/diazotheme/foundation/starter`` 
directory with following resources files:

::

    _ starter
      Provides the resources from "Foundation Starter Theme".
      _ manifest.cfg
      _ rules.xml


Foundation Example Theme
------------------------

The resources of this theme can be reached through

    ``/++theme++foundation``

There are placed at ``diazotheme.foundation/diazotheme/foundation/theme`` 
directory with following resources files:

::

    _ theme
      Provides the resources from "Foundation Example Theme".
      _ manifest.cfg
      _ preview.png
      _ rules.xml


Contribute
==========

- Issue Tracker: https://github.com/TH-code/diazotheme.foundation/issues
- Source Code: https://github.com/TH-code/diazotheme.foundation


License
=======

The project is licensed under the GPLv2.


Credits
-------

- Thijs Jonkman (t.jonkman at gmail dot com).


Amazing contributions
---------------------

- Leonardo J. Caballero G. aka macagua (leonardocaballero at gmail dot com).

You can find an updated list of package contributors on https://github.com/TH-code/diazotheme.foundation/contributors

.. _`Zurb Foundation CSS framework`: http://foundation.zurb.com/
.. _`Diazo`: http://diazo.org
.. _`plone.app.theming`: https://pypi.org/project/plone.app.theming/
.. _`diazoframework.foundation`: https://github.com/TH-code/diazoframework.foundation
.. _`diazotheme.foundation`: https://github.com/TH-code/diazotheme.foundation
