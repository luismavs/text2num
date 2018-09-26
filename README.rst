text2num
========

``text2num`` is a python package that provides functions and parser classes for:

- parsing numbers expressed as words in french and convert them to integer values;
- detect ordinal, cardinal and decimal numbers in a stream of french words and get their decimal digit representations.

Compatibility
-------------

Tested on python 3.6, 3.7.

Installation
------------

``text2num`` does not depend on any other third party package.

To install text2num in your (virtual) environment::

    pip install text2num

That's all folks!

Usage examples
--------------

Parse and convert
~~~~~~~~~~~~~~~~~

.. code-block:: python

    >>> from text_to_num import text2num
    >>> text2num('nonante-cinq')
    95

    >>> text2num('mille neuf cent quatre-vingt dix-neuf')
    1999

    >>> text2num("cinquante et un million cinq cent soixante dix-huit mille trois cent deux")
    51578302

    >>> text2num('mille mille deux cents')
    AssertionError


Find and transcribe
~~~~~~~~~~~~~~~~~~~

Any numbers, even ordinals.

.. code-block:: python

    >>> from text_to_num import alpha2digit
    >>> sentence = (
    ...         "Huit cent quarante-deux pommes, vingt-cinq chiens, mille trois chevaux, "
    ...         "douze mille six cent quatre-vingt-dix-huit clous.\n"
    ...         "Quatre-vingt-quinze vaut nonante-cinq. On tolère l'absence de tirets avant les unités : "
    ...         "soixante seize vaut septante six.\n"
    ...         "Nombres en série : douze quinze zéro zéro quatre vingt cinquante-deux cent trois cinquante deux "
    ...         "trente et un.\n"
    ...         "Ordinaux: cinquième troisième vingt et unième centième mille deux cent trentième.\n"
    ...         "Décimaux: douze virgule quatre-vingt dix-neuf, cent vingt virgule zéro cinq ; "
    ...         "mais soixante zéro deux."
    ...     )
    >>> print(alpha2digit(sentence))
    842 pommes, 25 chiens, 1003 chevaux, 12698 clous.
    95 vaut 95. On tolère l'absence de tirets avant les unités : 76 vaut 76.
    Nombres en série : 12 15 004 20 52 103 52 31.
    Ordinaux: 5ème 3ème 21ème 100ème 1230ème.
    Décimaux: 12,99, 120,05 ; mais 60 02.


Contribute
----------

Join us on https://github.com/allo-media/text2num