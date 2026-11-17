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

#### Wearable isLocated Location

* disjoint: `Wearble DisjointWith Location` <br />
  Nothing can be a wearable and a boyd part(location).
* Scoped domain: `isLocated some Location SubClassOf Wearable` <br />
  Anything located at a body location must be a wearable.
* Scoped range: `Wearable SubClassOf isLocated only Location` <br />
  Anything a wearable is located at must be a body location.
* Existential : `Wearable SubClassOf isLocated some Location` <br />
  Every wearable is located at at least one body location.

## Behavior Assessment
![Behavior Assessment module schema](../Schema/Behavior_Assessment.jpg)
### Axioms
#### Actor exhibits Behavior
* Disjoint: `Actor DisjointWith Behavior` <br />
  Nothing can be both an actor and a behavior.
* Scoped domain: `exhibits some Behavior SubClassOf Actor` <br />
  Anything that exhibits a behavior must be an actor.
* Scoped range: `Actor SubClassOf exhibits only Behavior` <br />
  Anything an actor exhibits must be a behavior.
* Structural tautology: `Actor SubClassOf exhibits min 0 Behavior` <br />
  An actor may exhibit zero or more behaviors.
* Existential: Behavior SubClassOf exhibits some Actor <br />
  Every behavior is exhibited by at least one actor.
  
#### Observation informs Interpretation
* Scoped domain: `informs some Behavior SubClassOf Interpretation` <br />
  Anything that informs a behavior is an observation or an behavior or interpretation.
* Scoped range: `Observation SubClassOf informs only Interpretation` <br />
  Anything an observation informs must be a behavior or an interpretation.
* Structural tautology: `Observation SubClassOf informs min 0 Behavior`<br />
  An observation may inform zero or more behaviors.

#### Expectation determines Interpretation
* Disjoint: `Expectation DisjointWith Interpretation` <br/>
  Nothing can be both an expectation and an interpretation.
* Scoped domain: `determines some Interpretation SubClassOf Expectation` <br/>
  Anything that determines an interpretation must be an expectation.
* Scoped range: `Expectation SubClassOf determines only Interpretation` <br />
  Anything an expectation determines must be an interpretation.
* Structural tautology: `Expectation SubClassOf determines min 0 Interpretation` <br />
  An expectation may determine zero or more interpretations.
* Existential: `Interpretation SubClassOf inverse(determines) some Expectation` <br />
 Every interpretation is judged against at least one expectation.

## Observation
![Observation module schema](../Schema/Observation.jpg)

### Axioms
#### Agent madeObservation Observation
* Disjoint: `Agent DisjointWith Observation` <br />
  Nothing can be both an agent and an observation.
* domain: `madeObservation some owl:Thing SubClassOf Agent` <br />
  Anything that made an observation must be an agent.
* Range: owl: `Thing SubClassOf madeObservation only Observation` <br />
  Whatever anything made must be an observation.
* Structural tautology: `Agent SubClassOf madeObservation min 0 Observation` <br />
  An agent may make zero or more observations.

#### Observation hasResult Result
* Disjoint: `Observation DisjointWith Result` <br />
  Nothing can be both an observation and a result.
* Domain: `hasResult owl:Thing SubClassOf Observation` <br/>
  Anything that has a result must be an observation.
* Range: `owl:Thing SubClassOf hasResult only Result` <br/>
  Anything an observation has as a result must be a result.
* Existential: `Observation SubClassOf hasResult some Resul` <br /> 
  Every observation has a result.
  
#### Observation hasFeatureOfInterest FeatureOfInterest
* Disjoint:  `Observation DisjointWith FeatureOfInterest` <br />
  Nothing can be both an observation and the thing it’s about.
* Scoped domain:  `hasFeatureOfInterest some FeatureOfInterest SubClassOf Observation` <br/>
  Anything that has a feature of interest must be an observation.
* Scoped range: `Observation SubClassOf hasFeatureOfInterest only FeatureOfInterest` <br/>
  Anything an observation is about must be a feature of interest.
* Existential: `Observation SubClassOf hasFeatureOfInterest some FeatureOfInterest` <br />
  Every observation is about at least one thing.
