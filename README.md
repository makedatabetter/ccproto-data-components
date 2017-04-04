# gid-list-applications

A data component that provides a list of applications associated with a given concept.  

    <gid-list-applications conceptId='1'></gid-list-applications>

For each application, the result set includes:

* application name
* application id
* count of unconfirmed columns identified as representing the given concept
* count of confirmed columns

Expectation is that UI components, when sorting this list in recommended order, will rank applications having the largest number of instances (confirmed + unconfirmed) above those having fewer.



# gid-list-databases

Supplies information about the databases associated with a given application, and a given concept.


    <gid-list-databases appId='1' conceptId='1'></gid-list-databases>


# gid-list-schemas

Supplies information about the schemas associated with a given database, and a given concept.


    <gid-list-schemas dbId='1' conceptId='1'></gid-list-schemas>


# gid-list-tables

Supplies information about the tables associated with a given schema, and a given concept.


    <gid-list-tables schemaId='1' conceptId='1'></gid-list-tables>


# gid-get-table-info

Supplies a list of columns (identifiers and labels) for a given table.


    <gid-get-table-info tableId='1'></gid-get-table-info>


# gid-get-column-concepts

A data component that supplies information about concepts related to a given column.  Returns a list of zero or more concepts ranked in descending order where the most likely represention is at the top of the list.

The ranking is based on assessments made either by the system or by a human.


    <gid-get-column-concepts columnId='1'></<gid-get-column-concepts>

# gid-get-column-samples

A data component to get sample values for a given column.


    <gid-get-column-samples columnId='1'></<gid-get-column-samples>