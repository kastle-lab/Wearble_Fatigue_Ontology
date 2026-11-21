# BIO - Behavior Interpretation Ontology

## Survey
![Survey module schema](../schema-diagrams/Survey/Survey.jpg)

### Axioms

#### Survey hasItem SurveyItem <br />

* disjoint: `Survey DisjointWith SurveyItem`

* scoped domain: `hasItem some SurveyItem SubClassOf Survey` <br />
Anything that has a SurveyItem must be a Survey

* Scoped range: `Survey SubClassOf hasItem only SurveyItem` <br />

* Existential : `Survey SubClassOf hasItem some SurveyItem` <br/>

* Qualified Scoped Funcationality: `Survey SubClassOf hasItem min 1 SurveyItem` <br />
  Survey has atleast one SurveyItem

#### Response answers SurveyItem <br />

* disjoint: `Response DisjointWith SurveyItem` <br />
  Nothing can be Response and a Survey question.
  
* Scoped domain: `answers some SurveyItem SubClassOf Response` <br />
Anything that answers a SurveyItem must be a Response.

* Scoped range: `Response SubClassOf answers only SurveyItem` <br />

* Existential: `Response SubclassOf answers some SurveyItem` <br />

* Inverse Existential: `SurveyItem SubClassOf inverse answers some Response` <br />

* Functionality: `Response SubClassOf answers min 1 SurveyItem` <br />
  Each response answers min one Survey question.
  
*Inverse Qualified Scoped Functionality: `SurveyItem SubClassOf inverse answers exactly 1 Response` <br /> 

#### Actor takesSurvey Survey <br />

* disjoint : `Actor DisjointWith Survey`

* scoped domain: `takesSurvey some Survey subclassOf Actor` <br />

* Scoped range: `Actor subClassOf takesSurvey only Survey` <br />

* Inverse Existential : `Survey SubClassOf Inverse answers some Actor` <br/>

* Structural Tautology: `Actor subClassOf takesSurvey min 0 Survey` <br />
  An Actor may take zero or more Survey.

## Instrumentation
![Instrumentation module schema](../schema-diagrams/Instrumentation/Instrumentation.jpg)

### Axioms 
#### Actor wears Wearable <br />

* disjoint: `Actor DisjointWith Wearable` <br />

* scoped domain: `wears some Wearable SubClassOf Actor` <br />

* scoped range: `Actor SubClassOf wears only Wearable` <br />

* Inverse Existential: `Wearable subClassOf inverse wears some Actor` <br />

* Structural Tautology: `Actor SubClassOf wears min 0 Wearable` <br />
  An Actor may wear zero or more Wearables.
  

#### Task requiresEquipment Equipment

* disjoint: `Task  DisjointWith Equipment` <br />
  Nothing can be both a Task and a piece of Equipment.

I THINK SO BUT DISCUSS
* scoped domain: `requiresEquipment some Equipment SubClassOf Task` <br />
Anything that requires Equipment must be a Task.

* scoped range: `Task SubClassOf requiresEquipment only Equipment` <br />
  Anything a Task requires must be Equipment.

* Structural Tautology: `Task SubClassOf requiresEquipment min 0 Equipment` <br />
  A Task may require zero or more Equipment.

#### Wearable isLocated Location

* disjoint: `Wearable DisjointWith Location` <br />
  Nothing can be a wearable and a body part(location).
  
* Scoped domain: `isLocated some Location SubClassOf Wearable` <br />
  Anything located at a body location must be a wearable.
  
* Scoped range: `Wearable SubClassOf isLocated only Location` <br />
  Anything a wearable is located at must be a body location.
  
* Existential : `Wearable SubClassOf isLocated some Location` <br />
  Every wearable is located at at least one body location.
  
* Qualified Scoped Functionality: `Wearable SubClassOf isLocated min 1 Location` <br />

## Behavior Assessment
![Behavior Assessment module schema](../schema-diagrams/Behavior-Assessment/Behavior_Assessment.jpg)
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
  
* Inverse Qualified Scoped Functionality: `Behavior SubClassOf inverse exhibits min 1 Actor` <br />
  Every behavior is exhibited by at least one actor.
  
#### Observation informs Interpretation
* Scoped domain: `informs some Interpretation SubClassOf Observation` <br />
  Anything that informs a behavior is an observation or an behavior or interpretation.
  
* Scoped range: `Observation SubClassOf informs only Interpretation` <br />
  Anything an observation informs must be a behavior or an interpretation.

* Inverse Qualified Scoped Functionality: `Interpretation SubClassOf inverse informs min 1 Observation` <br />
  
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
  
* Inverse Existential: `Interpretation SubClassOf inverse determines some Expectation` <br />
 Every interpretation is judged against at least one expectation.

## Observation
![Observation module schema](../schema-diagrams/Observation/Observation.jpg)

### Axioms
#### Agent madeObservation Observation
* Disjoint: `Agent DisjointWith Observation` <br />
  Nothing can be both an agent and an observation.
  
* domain: `madeObservation some Observation SubClassOf Agent` <br />
  Anything that made an observation must be an agent.
  
* Range: `Agent SubClassOf madeObservation only Observation` <br />
  Whatever anything made must be an observation.
  
* Inverse Qualified Scoped Functionality: `Observation SubClassOf inverse madeObservation exactly 1 Agent` <br />

* Structural tautology: `Agent SubClassOf madeObservation min 0 Observation` <br />
  An agent may make zero or more observations.

#### Observation hasResult Result
* Disjoint: `Observation DisjointWith Result` <br />
  Nothing can be both an observation and a result.
  
* Scoped Domain: `hasResult some Result SubClassOf Observation` <br/>
  Anything that has a result must be an observation.
  
* Scoped Range: `Observation SubClassOf hasResult only Result` <br/>
  Anything an observation has as a result must be a result.
  
* Existential: `Observation SubClassOf hasResult some Result` <br /> 
  Every observation has a result.
  
* Inverse Existential: `Result SubClassOf inverse hasResult some Observation` <br />

* Qualified Scoped Functionality: `Observation SubClassOf hasResult min 1 Result` <br />

* Inverse Qualified Scoped Functionality: `Result SubClassOf inverse hasResult exactly 1 Observation` <br />

  
#### Observation hasFeatureOfInterest FeatureOfInterest

* Disjoint:  `Observation DisjointWith FeatureOfInterest` <br />
  Nothing can be both an observation and the thing it’s about.
  
* Scoped domain:  `hasFeatureOfInterest some FeatureOfInterest SubClassOf Observation` <br/>
  Anything that has a feature of interest must be an observation.
  
* Scoped range: `Observation SubClassOf hasFeatureOfInterest only FeatureOfInterest` <br/>
  Anything an observation is about must be a feature of interest.
  
* Existential: `Observation SubClassOf hasFeatureOfInterest some FeatureOfInterest` <br />
  Every observation is about at least one thing.

* Qualified Scoped Functionality: `Observation SubClassOf hasFeatureOfInterest exactly 1 FeatureOfInterest` <br /> 

#### Observation observedProperty ObservableProperty
* Disjoint: `Observation DisjointWith ObservableProperty` <br />

* Scoped Domain: `ObservedProperty some ObservableProperty SubClassOf Observation` <br />

* Scoped Range: `Observation SubClassOf observedProperty only ObservableProperty` <br/>

* Existential: `Observation SubClassOf observedProperty some ObservableProperty` <br />

* Qualified Scoped Functionality: `Observation SubClassOf observedProperty exactly 1 ObservableProperty` <br /> 

## Goal-Task
![Goal-Task module schema](../Schema/Goal-Task.jpg)

### Axioms  
#### Goal scopedBy Task
* Disjoint: `Goal DisjointWith Task` <br />
  Nothing can be both a task and a goal.
* Scoped domain: `scopedBy some Task SubClassOf Goal` <br />
  Anything scoped by tasks must have a goal.
* Scoped range: `Goal SubClassOf scopedBy only Tasks` <br />
  Any goal scope must be a task.
* Existential: `Goal SubClassOf scopedBy some Task` <br />
  Every goal has at least one task.
* Structural tautology: `Goal SubClassOf scopedBy min 0 Task` <br />
  A goal may be scoped by zero or more tasks.
* Qualified Scoped Funcationality: `Goal SubClassOf scopedBy min 1 Task` <br />
  Goal has atleast one Task

#### Scenario hasGoal Goal
* Disjoint: `Scenario DisjointWith Goal` <br />
  Nothing can be both a scenario and a goal.
* Scoped domain: `hasGoal some Goal SubClassOf Scenario` <br />
  Anything that has a goal must have a scenario.
* Structural tautology: `Scenario SubClassOf scopedBy min 0 Goal` <br />
  A scenario may have zero or more goals. 
  
#### Scenario providesRole Role
* Disjoint: `Scenario DisjointWith Role` <br />
  Nothing can be both a scenario and a role.
* Scoped domain: `providesRole some Role SubClassOf Scenario` <br />
  Anything that has a role must have a scenario.
* Structural tautology: `Scenario SubClassOf providesRole min 0 Role` <br />
  A scenario may have zero or more roles.

  

