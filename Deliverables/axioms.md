# BIO - Behavior Interpretation Ontology

## Survey
![Survey module schema](../Schema/Survey.jpg)

### Axioms

#### Survey hasItem SurveyItem <br />

* disjoint: `Survey DisjointWith SurveyItem`

* domain: `hasItem some owl:Thing SubClassOf Survey` <br />

* global range: `owl:Thing SubClassOf hasItem only SurveyItem` <br />

* Qualified Scoped Funcationality: `Survey SubClassOf hasItem min 1 SurveyITem` <br />
Survey has atleast one SurveyItem

#### Response answers SurveyItem <br />

* disjoint: `Response DisjointWith SurveyItem`
Nothing can be Response and a Survey question.
* domain: `answers some owl:Thing SubClassOf Response` <br />

* global range: `owl:Thing SubClassOf answers only SurveyItem` <br />

* funcationality: `Response SubClassOf answers exactly 1 SurveyITem` <br />
Each response answers exactly one Survey question.

#### Actor takesSurvey Survey <br />

* disjoint : `Actor DisjointWith Survey`

* scoped domain: `takesSurvey some Agent subclassOf Survey` <br />

* global range: `owl:Thing subClassOf takesSurvey only Survey` <br />

* Structural Tautology: `Actor subClassOf takesSurvey min 0 Survey` <br />
An Actor may take zero or more Survey.

## Instrumentation
![Instrumentation module schema](../Schema/Instrumentation.jpg)

### Axioms 
#### Actor wears Wearable <br />

* disjoint: `Actor DisjointWith Wearable`

* scoped domain: `wears some Wearable SubClassOf Actor` <br />

* scoped range: `Actor SubClassOf wears only Wearable` <br />

* Structural Tautology: `Actor SuClassOf wears min 0 Wearable` <br />
An Actor may wear zero or more Wearables.

#### Task requiresEquipment Equipment

* disjoint: `Task  DisjointWith Equipment`
Nothing can be both a Task and a piece of Equipment.

* scoped domain: `requiresEquipment some Equipment SubClassOf Task` <br />

* scoped range: `Task SubClassOf requiresEquipment only Equipment` <br />
Anything a Task requires must be Equipment.

* Structural Tautology: `Task SuClassOf requiresEquipment min 0 Equipment` <br />
A Task may require zero or more Equipment.
