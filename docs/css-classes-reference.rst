CSS classes reference
=====================


Stylable classes
----------------

The general purpose classes are intended to be used for any language, but the
other classes may also be used when they are semantically correct.  For example
if you had a general purpose language that allowed inline URLs:

::

  var GOOGLE = https://www.google.com/


It would be reasonable to use the ``link`` class for this, even if your language
is not a markup language.  However, many themes might not be designed with this
in mind so a better choice might be ``string`` or perhaps ``string.link``.

+----------------------------------------------------------------------------------------+
| **General purpose**                                                                    |
+--------------------------+-------------------------------------------------------------+
| keyword                  | keyword in a regular Algol-style language                   |
+--------------------------+-------------------------------------------------------------+
| built_in                 | built-in or library object (constant, class,                |
|                          | function)                                                   |
+--------------------------+-------------------------------------------------------------+
| type                     | data type (in a language with syntactically                 |
|                          | significant types) (``string``, ``int``,                    |
|                          | ``array``, etc.)                                            |
+--------------------------+-------------------------------------------------------------+
| literal                  | special identifier for a built-in value                     |
|                          | (``true``, ``false``, ``null``, etc.)                       |
+--------------------------+-------------------------------------------------------------+
| number                   | number, including units and modifiers, if any.              |
+--------------------------+-------------------------------------------------------------+
| operator                 | operators: ``+``, ``-``, ``>>``, ``|``, ``==``              |
+--------------------------+-------------------------------------------------------------+
| punctuation              | aux. punctuation that should be subtly highlighted          |
|                          | (parentheses, brackets, etc.)                               |
+--------------------------+-------------------------------------------------------------+
| property                 | object property ``obj.prop1.prop2.value``                   |
+--------------------------+-------------------------------------------------------------+
| regexp                   | literal regular expression                                  |
+--------------------------+-------------------------------------------------------------+
| string                   | literal string, character                                   |
+--------------------------+-------------------------------------------------------------+
| subst                    | parsed section inside a literal string                      |
+--------------------------+-------------------------------------------------------------+
| symbol                   | symbolic constant, interned string, goto label              |
+--------------------------+-------------------------------------------------------------+
| class                    | relating to a class, typically paired with                  |
|                          | another scope such as ``title.class``                             |
+--------------------------+-------------------------------------------------------------+
| function                 | relating to a function, typically paired with               |
|                          | another scope such as ``title.function``                             |
+--------------------------+-------------------------------------------------------------+
| variable                 | variables                                                   |
+--------------------------+-------------------------------------------------------------+
| title                    | name of a class or a function                               |
+--------------------------+-------------------------------------------------------------+
| title.class              | name of a class (interface, trait, module, etc)             |
+--------------------------+-------------------------------------------------------------+
| title.function           | name of a function                                          |
+--------------------------+-------------------------------------------------------------+
| params                   | block of function arguments (parameters) at the             |
|                          | place of declaration                                        |
+--------------------------+-------------------------------------------------------------+
| comment                  | comments                                                    |
+--------------------------+-------------------------------------------------------------+
| doctag                   | documentation markup within comments                        |
+--------------------------+-------------------------------------------------------------+
| **Meta**                                                                               |
+--------------------------+-------------------------------------------------------------+
| meta                     | flags, modifiers, annotations, processing                   |
|                          | instructions, preprocessor directives, etc                  |
+--------------------------+-------------------------------------------------------------+
| meta-keyword             | keyword or built-in within meta construct                   |
+--------------------------+-------------------------------------------------------------+
| meta-string              | string within meta construct                                |
+--------------------------+-------------------------------------------------------------+
| **Tags, attributes, configs**                                                          |
+--------------------------+-------------------------------------------------------------+
| section                  | heading of a section in a config file, heading in           |
|                          | text markup                                                 |
+--------------------------+-------------------------------------------------------------+
| tag                      | XML/HTML tag                                                |
+--------------------------+-------------------------------------------------------------+
| name                     | name of an XML tag, the first word in an                    |
|                          | s-expression                                                |
+--------------------------+-------------------------------------------------------------+
| attr                     | name of an attribute with no language defined               |
|                          | semantics (keys in JSON, setting names in .ini),            |
|                          | also sub-attribute within another highlighted               |
|                          | object, like XML tag                                        |
+--------------------------+-------------------------------------------------------------+
| attribute                | name of an attribute followed by a structured               |
|                          | value part, like CSS properties                             |
+--------------------------+-------------------------------------------------------------+
| **Text Markup**                                                                        |
+--------------------------+-------------------------------------------------------------+
| bullet                   | list item bullet                                            |
+--------------------------+-------------------------------------------------------------+
| code                     | code block                                                  |
+--------------------------+-------------------------------------------------------------+
| emphasis                 | emphasis                                                    |
+--------------------------+-------------------------------------------------------------+
| strong                   | strong emphasis                                             |
+--------------------------+-------------------------------------------------------------+
| formula                  | mathematical formula                                        |
+--------------------------+-------------------------------------------------------------+
| link                     | hyperlink                                                   |
+--------------------------+-------------------------------------------------------------+
| quote                    | quotation or blockquote                                     |
+--------------------------+-------------------------------------------------------------+
| **CSS**                                                                                |
+--------------------------+-------------------------------------------------------------+
| selector-tag             | tag selector                                                |
+--------------------------+-------------------------------------------------------------+
| selector-id              | #id selector                                                |
+--------------------------+-------------------------------------------------------------+
| selector-class           | .class selector                                             |
+--------------------------+-------------------------------------------------------------+
| selector-attr            | [attr] selector                                             |
+--------------------------+-------------------------------------------------------------+
| selector-pseudo          | :pseudo selector                                            |
+--------------------------+-------------------------------------------------------------+
| **Templates**                                                                          |
+--------------------------+-------------------------------------------------------------+
| template-tag             | tag of a template language                                  |
+--------------------------+-------------------------------------------------------------+
| template-variable        | variable in a template language                             |
+--------------------------+-------------------------------------------------------------+
| **diff**                                                                               |
+--------------------------+-------------------------------------------------------------+
| addition                 | added or changed line                                       |
+--------------------------+-------------------------------------------------------------+
| deletion                 | deleted line                                                |
+--------------------------+-------------------------------------------------------------+

A note on multi-scope classes
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Some scope names above have a ``.`` in them.  We use this notation to specify
multiple scopes.  In the generated HTML this will output two separate classes.
For example, Lets say the scope name is ``title.class``.  The generated HTML
would be:

::

  class <span class="hljs-title hljs-class">Render</span>

Render is a ``title``, the title of a ``class`` in particular. Some definitions
still use nested rules/tags to do this, but the preferred way is now to handle
this with the new multi-scope classes and simplify the language definitions when
possible.


A note on newer classes
^^^^^^^^^^^^^^^^^^^^^^^

Some classes have been added more recently and do not enjoy universal theme
support.  For themes without support, these items will simply not be
highlighted.  This doesn't mean not to use them, only that they will be
highlighted better as support improves over time.

A list of these classes:

- operator
- punctuation
- property


Reserved classes
^^^^^^^^^^^^^^^^

The below classes (ReasonML) are left here for documentation purposes but may
not be used in other grammars because they are very poorly supported by all
themes.

If you'd like to help out with the larger issue here:

- https://github.com/highlightjs/highlight.js/issues/2521
- https://github.com/highlightjs/highlight.js/issues/2500

+--------------------------+---------------------------------------------------+
| **ReasonML**                                                                 |
+--------------------------+---------------------------------------------------+
| pattern-match            | pattern matching matchers                         |
+--------------------------+---------------------------------------------------+
| typing                   | type signatures on function parameters            |
+--------------------------+---------------------------------------------------+
| constructor              | type constructors                                 |
+--------------------------+---------------------------------------------------+
| module-access            | scope access into a module                        |
+--------------------------+---------------------------------------------------+
| module                   | module reference within scope access              |
+--------------------------+---------------------------------------------------+


Language names and aliases
--------------------------

The language names and aliases table has moved to `SUPPORTED_LANGUAGES.md <https://github.com/highlightjs/highlight.js/blob/main/SUPPORTED_LANGUAGES.md>`_.
