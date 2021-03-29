# Design Principles 

The following conventions describe the Python implementation. Matlab conventions are similar and will be described separately.

## DataJoint Schemas
DataJoint allows creating *database schemas*, which are namespaces for collections of related tables. 

The following commands declare a new schema and create the object named `schema` to reference the database schema.
```python
import datajoint as dj
schema = dj.schema('<schema_name>')
```

We follow the convention of having only one schema defined per Python module. 
Then such a module becomes a "DataJoint schema" comprising a python module  with a corresponding database schema. 

The module's `schema` object is then used as the decorator for classes that define tables in the database. 

## Elements 
An Element is a software package defining one or more DataJoint schemas serving a particular purpose. 
By convention, such packages are hosted in individual GitHub repositories.
For example, Element `element_calcium_imaging` is hosted at https://github.com/datajoint/element-calcium-imaging, 
and contains two DataJoint schemas: `scan` and `imaging`.
 

### Deferred schemas 
A *deferred schema* is one in which the name of the database schema name is not specified. 
This module does not declare schema and tables upon import. 
Instead, they are declared by calling `schema.activate('<schema_name>')` after import. 

By convention, all modules corresponding to deferred schema must declare the function `activate` which in turn calls `schema.activate`. 

Thus typical Element modules begin with 

```python
import datajoint as dj
schema = dj.schema()

def activate(schema_name):
	schema.activate(schema_name)
```

However, many activate functions perform other work associated with activating the schema such as activating other schemas upstream.

### Linking Module

To make the code more modular with fewer dependencies, Elements' modules do not use `import` to connect to modules upstream. 
Instead, all prerequisites must be defined in a "linking module" and passed to the module's `activate` function.

For instance, to be activated, the `scan` module of the Element `element_calcium_imaging` requires an existing `Session` table. 
A module containing `Session` much be passed into `element_calcium_imaging.scan.activate(..., linking_module=<module>)`.

Thus, typical activation of Elements' modules takes the form of

```python
from element_calcium_imaging import scan     # `scan` is a deferred schema of `element_calcium_imaging`, to be activated

# Activation of `scan` requires an declared table named Session

schema = dj.schema('experiment')


@schema
class Session(dj.Manual):
    definition = """
    subject_name: varchar(36)
    session_id: int
    """
    
# Activating the `scan` schema

scan_schema_name = 'scan'
scan.activate(scan_schema_name, linking_module=__name__)  # "__name__" indicates the current module which contains `Session`
```
