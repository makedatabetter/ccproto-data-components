# Data Components

| Data Components  | Specifications | Source | Demo & Docs |
| ------------- | ------------- | -------- | ------- |
| gid-list-concepts| [View Specs](https://github.com/makedatabetter/ccproto-data-components#gid-list-concepts) | [View Source](https://github.com/makedatabetter-dev/gid-list-concepts)| [View Demo](https://makedatabetter-dev.github.io/gid-list-concepts/) | 
| gid-concept-details| [View Specs](https://github.com/makedatabetter/ccproto-data-components#gid-concept-details) | [View Source](https://github.com/makedatabetter-dev/gid-concept-details)| [View Demo](https://makedatabetter-dev.github.io/gid-concept-details/) | 
| gid-curate-concept| [View Specs](https://github.com/makedatabetter/ccproto-data-components#gid-curate-concept)  | 
| gid-concept-health|  |  
| gid-columns|  |  [View Source](https://github.com/makedatabetter-dev/gid-columns)| |
| gid-concept-service|  |  [View Source](https://github.com/makedatabetter-dev/gid-concept-service)| | 
| gid-table-samples| | [View Source](https://github.com/makedatabetter-dev/gid-table-samples)| [View Demo](https://makedatabetter-dev.github.io/gid-table-samples/) | 
| gid-list-entities| |  [View Source](https://github.com/makedatabetter-dev/gid-list-entities)| |
| gid-recommend-concepts|  |  [View Source](https://github.com/makedatabetter-dev/gid-recommend-concepts)| |

# Data Components Specifications

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

Input:

- User Id

Output:

- List of concepts with key metadata (items being displayed on listing page)


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
    
Input:
- User Id
- Concept Id

Output:
- Key Metadata
- Concept Detail


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

## gid-curate-concept

A data component to curate concept

    <gid-curate-concept conceptId='1' userId='1'></<gid-curate-concept>

API endpoint:

    GET /concepts/{id}

Input:

- User Id

- Concept Id

- List of recommended applications to start with

- Trigger that user has switched from define to explore

- Explicit yes or no on most of the synonyms, patterns and concepts

- Explicit yes or no on most of the example columns and some of the example values

- Search string for synonyms, patterns or related concepts

Output:
- 5 synonyms (with likelihood)
- 5 patterns (with likelihood)
- 5 related concepts (with likelihood)

- list of 10 example columns and 100 example values (prioritised by relevance)

- output 2 + revised list of synonyms, patterns and related concepts 

- search results
