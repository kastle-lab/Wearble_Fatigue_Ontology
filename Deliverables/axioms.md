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
