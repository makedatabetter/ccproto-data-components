## gid-list-applications

A data component that provides a list of applications associated with a given concept.  

    <gid-list-applications conceptId='1'></gid-list-applications>

For each application, the result set includes:

* application name
* application id
* count of unconfirmed columns identified as representing the given concept
* count of confirmed columns

Expectation is that UI components, when sorting this list in recommended order, will rank applications having the largest number of instances (confirmed + unconfirmed) above those having fewer.



## gid-list-databases

Supplies information about the databases associated with a given application, and a given concept.


    <gid-list-databases appId='1' conceptId='1'></gid-list-databases>


## gid-list-schemas

Supplies information about the schemas associated with a given database, and a given concept.


    <gid-list-schemas dbId='1' conceptId='1'></gid-list-schemas>


## gid-list-tables

Supplies information about the tables associated with a given schema, and a given concept.


    <gid-list-tables schemaId='1' conceptId='1'></gid-list-tables>


## gid-get-table-info

Supplies a list of columns (identifiers and labels) for a given table.


    <gid-get-table-info tableId='1'></gid-get-table-info>


## gid-get-column-concepts

A data component that supplies information about concepts related to a given column.  Returns a list of zero or more concepts ranked in descending order where the most likely represention is at the top of the list.

The ranking is based on assessments made either by the system or by a human.


    <gid-get-column-concepts columnId='1'></<gid-get-column-concepts>

## gid-get-column-samples

A data component to get sample values for a given column.


    <gid-get-column-samples columnId='1'></<gid-get-column-samples>


# Data components for Information Architect > Concepts


## gid-list-concepts

A data component to get list of concepts and its metadata for given user id

    <gid-list-concepts userId='1'></<gid-list-concepts>

API endpoint:

    GET /concepts

The output of this components will be as follows:

    {
      "concepts": [
        {
          "id": "100462",
          "label": "CASE-NUMBER",
          "owner": {
            "id": "111001",
            "label": "Angela"
          },
          "predictedColumns": 0,
          "confirmedColumns": 0,
          "eta": 0,
          "coverage": 0,
          "impactArea": [
            {
              "id": "120002",
              "label": "Credit Risk"
            },
            {
              "id": "120001",
              "label": "GDPR"
            }
          ],
          "classificationAccuracyPercentage": 5,
          "applications": [
            {
              "id": "100492",
              "label": "Universal Biller"
            },
            {
              "id": "100252",
              "label": "Supplier Management Program"
            },
            {
              "id": "100495",
              "label": "Field Service Support"
            },
            {
              "id": "100447",
              "label": "Contract Mgmt System"
            }
          ]
        }    
      ]
    }

## gid-concept-details

A data component to get detailed information for a given concept and user id

    <gid-concept-details conceptId='1' userId='1'></<gid-concept-details>

API endpoint:

    GET /concepts/{id}

The output of this components will be as follows:

    {
      "concept": {
        "id": "100462",
        "label": "FICO-Score",
        "owner": {
          "id": "111001",
          "label": "Angela"
        },
        "predictedColumns": 5,
        "confirmedColumns": 3,
        "eta": 0,
        "coverage": 0.001,
        "impactArea": [
          {
            "id": "120002",
            "label": "Credit Risk"
          },
          {
            "id": "120001",
            "label": "GDPR"
          }
        ],
        "classificationAccuracyPercentage": 5,
        "applications": [
          {
            "id": "100492",
            "label": "Universal Biller"
          },
          {
            "id": "100252",
            "label": "Supplier Management Program"
          }
        ],
        "synonyms": [
          {
            "id": "100052",
            "label": "DOB",
            "relevance": 45,
            "verified": "Y"
          },
          {
            "id": "100053",
            "label": "Birthday",
            "relevance": 65,
            "verified": "N"
          }
        ],
        "patterns": [
          {
            "id": "100152",
            "label": "DD/MM/YY",
            "relevance": 37,
            "verified": "F"
          },
          {
            "id": "100153",
            "label": "MM/YY/DD",
            "relevance": 54,
            "verified": "Y"
          }
        ],
        "relatedConcepts": [
          {
            "id": "100652",
            "label": "First Name",
            "relevance": 44,
            "verified": "Y"
          },
          {
            "id": "100653",
            "label": "Last Name",
            "relevance": 32,
            "verified": "Y"
          }
        ],
        "exampleValues": [
          {
            "id": "200652",
            "label": "21/03/2007",
            "relevance": 90,
            "verified": "Y"
          },
          {
            "id": "200653",
            "label": "08/07/2006",
            "relevance": 80,
            "verified": "Y"
          }
        ],
        "exampleColumns": [
          {
            "id": "300652",
            "label": "DOB",
            "relevance": 90,
            "verified": "Y"
          },
          {
            "id": "300653",
            "label": "BIRTH_DAY",
            "relevance": 80,
            "verified": "Y"
          },
          {
            "id": "300654",
            "label": "ORDER_DATE",
            "relevance": 50,
            "verified": "Y"
          }
        ]
      }
    }
