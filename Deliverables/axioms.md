# BIO - Behavior Interpretation Ontology

## Survey
![Survey module schema](../Schema/Survey.jpg)

### Axioms

## Survey hasItem SurveyItem <br />

disjoint: `Survey DisjointWith SurveyItem`

domain: `hasItem some owl:Thing SubClassOf Survey` <br />

global range: `owl:Thing SubClassOf hasItem only SurveyItem` <br />

Qualified Scoped Funcationality: `Survey SubClassOf hasItem min 1 SurveyITem` <br />


## Response answers SurveyItem <br />

disjoint: `Response DisjointWith SurveyItem`

domain: `answers some owl:Thing SubClassOf Response` <br />

global range: `owl:Thing SubClassOf answers only SurveyItem` <br />

funcationality: `Response SubClassOf answers exactly 1 SurveyITem` <br />


## Actor takesSurvey Survey <br />

disjoint : `Actor DisjointWith Survey`

scoped domain: `takesSurvey some Agent subclassOf Survey` <br />

global range: `owl:Thing subClassOf takesSurvey only Survey` <br />

Structural Tautology: `Actor subClassOf takesSurvey min 0 Survey` <br />


## Instrumentation
![Instrumentation module schema](../Schema/Instrumentation.jpg)

### Axioms 
## Actor wears Wearable <br />

disjoint: `Actor DisjointWith Wearable`

scoped domain: `wears some Wearable SubClassOf Actor` <br />

scoped range: `Actor SubClassOf wears only Wearable` <br />

Structural Tautology: `Actor SuClassOf wears min 0 Wearable` <br />


## Task requires Equipment

disjoint: `Task  DisjointWith Equipment`

scoped domain: `requires some Equiment SubClassOf Task` <br />

scoped range: `Task SubClassOf requires only Equipment` <br />

Structural Tautology: `Task SuClassOf requires min 0 Equipment` <br />

