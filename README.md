ReadProperty
============
Read properties from a BACNet/IP device. This block does not respond to any `whois` nor data-sharing requests. For every signal processed, a new requst is made to the target device and a single value read.

Properties
----------
- **address**: A string of the IP address (optional subnet mask and port number) of target device. For example, `192.168.100.100/24:47808`. Hostnames are not supported, raises `ValueError` if the supplied address cannot be parsed.
- **array_index**: If the value being read is inside an array, optionally specify the index of the desired value.
- **instance_num**: Which instance of the Object Type to read.
- **my_address**: Address to bind to receive unicast messages from BACNet devices.
- **my_object_instance**: 22-bit integer unique to all devices on this network, used to create a 32-bit device `object_identifer`.
- **my_vendor_id**: If you have an official BACNet Vendor ID put it here, otherwise use an arbitrary integer.
- **object_type**: One of the standard BACNet Object Types (for example `analogValue`, note the use of camelCase capitalization without spaces). Vendor-defined custom-objects are not supported. Raises `ValueError` if not a recognized object type.
- **property_id**: One of the defined Properties for this object type. Raises `ValueError` if not a valid property for this type.
- **results_field**: Attribute of the outgoing signal to store the value read from the target device.

Inputs
------
- **default**: Any list of Signals, one property is read for each signal.

Outputs
-------
- **default**: The same list of signals, enriched with the attribute defined by `results_field`, containing the result of this request, and key:value pairs in `details` describing the request.

Commands
--------
None

