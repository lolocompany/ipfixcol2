============================
 Extender (intermediate plugin)
============================

This intermediate plugin extends IPFIX records by adding new fields to the existing ones using user-defined expressions.


Example configuration
---------------------

.. code-block:: xml

    <intermediate>
      <name>Extenders</name>
      <plugin>extender</plugin>
      <params>
        <expr>dot1qCustomerVlanId == 0</expr>
        <id>VRFname=default</id>
      </params>
    </intermediate>

The above sample adds a new string field ``VRFname=default`` to each IPFIX record if the existing field ``dot1qCustomerVlanId`` equals zero.


Parameters
----------

``expr``
    The filter expression to evaluate.

``id``
    The identifier string to be added to the record when the expression evaluates to true.


Supported operations
--------------------

Comparisons
    - Operators: ``==``, ``<``, ``>``, ``<=``, ``>=``, ``!=``
    - Default: ``==`` (if the operator is omitted)

Substring Matching
    - Operator: ``contains``
    - Example: ``DNSName contains "example"``

Arithmetic
    - Operators: ``+``, ``-``, ``*``, ``/``, ``%``

Bitwise Logic
    - Operators: ``~`` (not), ``|`` (or), ``&`` (and), ``^`` (xor)

List Membership
    - Operator: ``in``
    - Example: ``port in [80, 443]``

Logical Operators
    - Operators: ``and``, ``or``, ``not``