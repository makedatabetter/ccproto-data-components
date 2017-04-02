# mdb-list-applications

A data component that provides a list of applications associated with a given concept.  

    <mdb-list-applications conceptId='1'></mdb-list-applications>

For each application, the result set includes:

* application name
* application id
* count of unconfirmed instances
* count of confirmed instance

Expectation is that UI components, when sorting this list in recommended order, will rank applications having the largest number of instances (confirmed + unconfirmed) above those having fewer.



# mdb-list-databases

Supplies information about the databases associated with a given application, and a given concept.


    <mdb-list-databases appId='1' conceptId='1'></mdb-list-databases>


# mdb-list-schemas

Supplies information about the schemas associated with a given database, and a given concept.


    <mdb-list-schemas dbId='1' conceptId='1'></mdb-list-schemas>


# mdb-list-tables

Supplies information about the tables associated with a given schema, and a given concept.


    <mdb-list-tables schemaId='1' conceptId='1'></mdb-list-tables>


# mdb-get-table-info

Supplies a list of columns (identifiers and labels) for a given table.


    <mdb-get-table-info tableId='1'></mdb-get-table-info>


# mdb-get-column-concepts

A data component that supplies information about concepts related to a given column.  Returns a list of zero or more concepts ranked in descending order where the most likely represention is at the top of the list.

The ranking is based on assessments made either by the system or by a human.


    <mdb-get-column-concepts columnId='1'></<mdb-get-column-concepts>

# mdb-get-column-samples

A data component to get sample values for a given column.


    <mdb-get-column-samples columnId='1'></<mdb-get-column-samples>