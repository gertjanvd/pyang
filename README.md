[![Build Status](https://travis-ci.org/mbj4668/pyang.svg?branch=master)](https://travis-ci.org/mbj4668/pyang)
[![Coverage Status](https://coveralls.io/repos/mbj4668/pyang/badge.svg)](https://coveralls.io/r/mbj4668/pyang)

## News ##

**2019-06-11 - Version 2.0.1 released**

  * this is a pure bug fix release


**2019-05-29 - Version 2.0 released**

  * pyang now has a proper XPath 1.0 parser, which means that it will
    detect more XPath errors, and produce warnings for XPath
    expressions that for example refer to unknown nodes.

  * pyang -f yang now keeps comments by default.  use
    the parameter --yang-remove-comments to remove them.

  * updated the IETF plugin to check RFC 8407 guidelines.

  * updated the IETF plugin to check for the license text and
    RFC 2119/8174 boilerplate text.

  * for python coders: non backwards compatible change in the
    pyang.xpath module.  the function xpath.tokens() has been replaced
    by pyang.xpath_lexer.scan(), but it also return tokens in a new
    format.

  * or python coders: non backwards compatible change in
    statements.add_xpath_function().  this function now takes
    three parameters, instead of just one.

  * ... and various other enhancements and bug fixes, see CHANGES.

See below for previous releases.

---


## Overview ##

YANG ([RFC 7950](http://tools.ietf.org/html/rfc7950)) is a data modeling language for NETCONF ([RFC 6241](http://tools.ietf.org/html/rfc6241)), developed by the IETF [NETMOD](http://www.ietf.org/html.charters/netmod-charter.html) WG.

pyang is a YANG validator, transformator and code generator, written in python. It can be used to validate YANG modules for correctness, to transform YANG modules into other formats, and to generate code from the modules.

## Installation ##

Pyang can be installed from [PyPI](https://pypi.python.org/pypi):

```
# pip install pyang
```

### Compatibility ###

pyang is compatible with the following IETF RFCs:

  * [RFC 6020](http://tools.ietf.org/html/rfc6020)
  * [RFC 6087](http://tools.ietf.org/html/rfc6087)
  * [RFC 6110](http://tools.ietf.org/html/rfc6110)
  * [RFC 6643](http://tools.ietf.org/html/rfc6643)
  * [RFC 7950](http://tools.ietf.org/html/rfc7950)
  * [RFC 7952](http://tools.ietf.org/html/rfc7952)
  * [RFC 8040](http://tools.ietf.org/html/rfc8040)
  * [RFC 8407](http://tools.ietf.org/html/rfc8407)

## Features ##

  * Validate YANG modules.
  * Convert YANG modules to YIN, and YIN to YANG.
  * Translate YANG data models to DSDL schemas, which can be used for
    validating various XML instance documents. See
    [InstanceValidation](https://github.com/mbj4668/pyang/wiki/InstanceValidation).
  * Translate YANG data models to XSD.
  * Generate UML diagrams from YANG models. See
    [UMLOutput](https://github.com/mbj4668/pyang/wiki/UMLOutput) for
    an example.
  * Generate compact tree representation of YANG models for quick
    visualization. See
    [TreeOutput](https://github.com/mbj4668/pyang/wiki/TreeOutput) for
    an example.
  * Generate a skeleton XML instance document from the data model.
  * Schema-aware translation of instance documents encoded in XML to
    JSON and vice-versa. See
    [XmlJson](https://github.com/mbj4668/pyang/wiki/XmlJson).
  * Plugin framework for simple development of other outputs, such as
    code generation.


---


## Documentation ##

See [Documentation](https://github.com/mbj4668/pyang/wiki/Documentation).


---

## Previous releases ##

**2019-01-21 - Version 1.7.8 released**

  * reverted method signature change for Repository.get_module_from_handle().
    it now has the same signature as in 1.7.5.

  * fixed bug in check_update when there were more than one augment for
    the same target node.

**2019-01-17 - Version 1.7.7 released**

  * fixed a bug in -f yang formatting

See below for previous releases.

**2019-01-17 - Version 1.7.6 released**

  * better formatting of YANG modules with -f yang

  * new type of plugin ("transform") to make transformations on the
    representation of the YANG module

  * ... and various other enhancements and bug fixes, see CHANGES.

**2018-04-25 - Version 1.7.5 released**

  * tree plugin updated to align with RFC 8340

  * better formatting of YANG modules with -f yang

  * reduced memory usage

  * ... and various other enhancements and bug fixes, see CHANGES.

**2018-02-23 - Version 1.7.4 released**

  * tree plugin updated to align with draft-ietf-netmod-yang-tree-diagrams-05

  * ... and various other enhancements and bug fixes, see CHANGES.

**2017-06-27 - Version 1.7.3 released**

  * Handle multiple rc:yang-data statements.  This bug caused
    validation of ietf-restconf, or any module that imported
    ietf-restconf, to fail.

**2017-06-14 - Version 1.7.2 released**

  * Added support for external plugins, using setuptools entry_points,
    with the entry point "pyang.plugin".

  * ... and various other enhancements and bug fixes, see CHANGES.

**2016-11-02 - Version 1.7.1 released**

  * This is mainly a bug fix release, see CHANGES for details.

**2016-06-16 - Version 1.7 released**
  * Support for YANG 1.1, with the exception of the new submodule scoping rules. 


**2015-10-06 - Version 1.6 released**

  * pyang can now be installed via [PyPi](https://pypi.python.org/pypi).

  * A new plugin 'lint' has been added. It checks if a module follow
    the generic guidelines defined in RFC 6087.  The 'ietf' plugin
    still exists, but is rewritten to use the new 'lint' plugin.

  * By default, pyang now scans the YANG module path recursively,
    i.e., it searches for YANG modules also in subdirectories to the
    directories in the load path.  This behavior can be disabled with
    '--no-path-recurse'.

  * A bash completions file has been added.

  * ... and various other enhancements and bug fixes, see CHANGES.

**2014-11-18 - Version 1.5 released**

  * A new plugin 'check-update' has been added. It can be used to check if a new revision of a module follows the update rules from RFC 6020.

  * A new plugin 'omni' has been added.  It generates an OmniGraffle script file from a model.

  * ... and various other enhancements and bug fixes.

**2013-11-11 - Version 1.4.1 released**
  * Exactly as 1.4, but fixed to that it works with Python 3.

**2013-10-24 - Version 1.4 released**
  * lots of bugfixes

**2013-01-31 - Version 1.3 released**
  * New plugins: hypertree, jstree, jsonxsl, jtox
  * lots of bugfixes

**2011-07-27 - Version 1.2 released**

**2011-02-16 - Version 1.1 released**

  * A new UML plugin has been added. It is used to generate UML
    diagrams for visualization of YANG data models.  See
    [UMLOutput](https://github.com/mbj4668/pyang/wiki/UMLOutput) for
    an example.
  * The DSDL plugin is updated to [RFC 6110](http://tools.ietf.org/html/rfc6110)
  * ... and various bug fixes.
