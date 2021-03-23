# Design Principles 

The following conventions describe the Python implementation. Matlab conventions are similar and will be described separately.

## DataJoint Schemas
A DataJoint schema is a combination of a Python module and a database schema. For convenience, both are typically similarly named.
The Python module typically begins with 

```python
import datajoint as dj
schema = dj.schema('<schema_name>')
```

The `schema` object is then used as the decorator for classes that define tables in the database. 

These types of modules declare the schema and its tables upon the first import. 

## Elements 

An Element is a software package defining one or more DataJoint schemas serving a particular purpose. 
By convention, such packages are hosted in individual GitHub repositories under the same name as the package name. 
For example, Element `element_calcium_imaging` is hosted at https://github.com/datajoint/element-calcium-imaging, 
and contains two modules: `scan` and `imaging`.
 

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

A *deferred schema* may require a set of prerequisites to be activated, 
these can be in the form of declared upstream DataJoint tables or utility functions. 
For instance, to be activated, the `scan` module of the Element `element_calcium_imaging` requires an existing `Session` table. 

These prerequisites can be provided by specifying in the `linking_module` argument the module containing them, 
most often the current module calling the `.activate()` itself. 
Thus, typical activation of Elements' modules takes the form of

```python
	from element-session import session
	from element-calcium-imaging import scan
	
	scan_schema_name = 'scan'
	
	scan.activate(scan_schema_name, linking_module=__name__)
```

