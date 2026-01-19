============================
 Extender (intermediate plugin)
============================

This intermediate plugin extends IPFIX records by adding new fields based on existing ones using user-defined expressions.


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

The above sample adds a new string field ``VRFname=default`` to each IPFIX record, if the existing field ``dot1qCustomerVlanId`` equals zero.


Parameters
----------

:``expr``:
    The filter expression.
:``id``:
    The identifier string to be added when the expression evaluates to true.
