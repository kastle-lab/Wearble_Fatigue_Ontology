# BIO - Behavior Interpretation Ontology

## Survey
![Survey module schema](../schema-diagrams/Survey/Survey.jpg)

### Axioms

#### Survey hasItem SurveyItem <br />
* disjoint: `Survey DisjointWith SurveyItem`
Nothing can be a Survey and a SurveyItem.

* scoped domain: `hasItem some SurveyItem SubClassOf Survey` <br />
Anything that has a SurveyItem must be a Survey

* Scoped range: `Survey SubClassOf hasItem only SurveyItem` <br />
Any Survey must have a Survey Item.

* Existential : `Survey SubClassOf hasItem some SurveyItem` <br/>

* Qualified Scoped Funcationality: `Survey SubClassOf hasItem min 1 SurveyItem` <br />
  Survey has atleast one SurveyItem


#### Response answers SurveyItem <br />

* disjoint: `Response DisjointWith SurveyItem` <br />
  Nothing can be Response and a Survey question.
  
* Scoped domain: `answers some SurveyItem SubClassOf Response` <br />
Anything that answers a SurveyItem must be a Response.

* Scoped range: `Response SubClassOf answers only SurveyItem` <br />
Any Response must answer a SurveyItem.

* Existential: `Response SubclassOf answers some SurveyItem` <br />

* Inverse Existential: `SurveyItem SubClassOf inverse answers some Response` <br />

* Functionality: `Response SubClassOf answers min 1 SurveyItem` <br />
  Each response answers min one Survey question.
  
*Inverse Qualified Scoped Functionality: `SurveyItem SubClassOf inverse answers exactly 1 Response` <br /> 


#### Actor takesSurvey Survey <br />

* disjoint : `Actor DisjointWith Survey`
Nothing can be both an Actor and a Survey

* scoped domain: `takesSurvey some Survey subclassOf Actor` <br />
Anything that takes a Survey must be an Actor.

* Scoped range: `Actor subClassOf takesSurvey only Survey` <br />
Anything that an Actor takes must be a Survey.

* Inverse Existential : `Survey SubClassOf Inverse answers some Actor` <br/>

* Structural Tautology: `Actor subClassOf takesSurvey min 0 Survey` <br />
  An Actor may take zero or more Surveys.


## Instrumentation
![Instrumentation module schema](../schema-diagrams/Instrumentation/Instrumentation.jpg)

### Axioms 
#### Actor wears Wearable <br />

* disjoint: `Actor DisjointWith Wearable` <br />
Nothing can be both an Actor and a Wearable.

* scoped domain: `wears some Wearable SubClassOf Actor` <br />
Anything that wears a Wearable must be an Actor.

* scoped range: `Actor SubClassOf wears only Wearable` <br />
Anything an actor wears but be a wearable.

* Inverse Existential: `Wearable subClassOf inverse wears some Actor` <br />

* Structural Tautology: `Actor SubClassOf wears min 0 Wearable` <br />
  An Actor may wear zero or more Wearables.
  

#### Task requiresEquipment Equipment

* disjoint: `Task  DisjointWith Equipment` <br />
  Nothing can be both a Task and a piece of Equipment.

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


#### Platform hosts Sensor

* disjoint: `Platform DisjointWith Sensor` <br />
  Nothing can be a platform and a sensor.
  
* Scoped range: `Platform SubClassOf hosts only Sensor` <br />
  Anything a sensor is located at must be a platform.

* Functionality: Platform SubClassOf hosts min 1 Sensor
Each platform hosts a minimum of one sensor.


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
NEED TO DISCUSS
* Scoped domain: `informs some Interpretation SubClassOf Observation` <br />
  Anything that informs a interpretation is an observation or a behavior.

* Scoped range: `Observation SubClassOf informs only Interpretation` <br />
  Anything an observation informs must be a behavior or an interpretation.

* Inverse Qualified Scoped Functionality: `Interpretation SubClassOf inverse informs min 1 Observation` <br />
  Every interpretation is informed by at least one observation.
  
* Structural tautology: `Observation SubClassOf informs min 0 Interpretation`<br />
  An observation may inform zero or more interpretations.


#### Behavior informs Interpretation
NEED TO DISCUSS
* Scoped domain: `informs some Interpretation SubClassOf Behavior` <br />
  Anything that informs an interpretation is a behavior or an observation.
  
* Scoped range: `Behavior SubClassOf informs only Interpretation` <br />
  Anything a behavior informs must be an interpretation.

* Inverse Qualified Scoped Functionality: `Interpretation SubClassOf inverse informs min 1 Behavior` <br />
  Every interpretation is informed by atleast one behavior.
  
* Functionality: Behavior SubClassOf informs min 1 Interpretation
  Each behavior informs min one interpretation.


#### Interpretation informs Behavior
* Scoped domain: `informs some Behavior SubClassOf Interpretation` <br />
  Anything that informs a behavior is an interpretation.

* Scoped range: `Interpretation SubClassOf informs only Behavior` <br />
  Anything an interpretation informs must be a behavior.

* Inverse Qualified Scoped Functionality: `Behavior SubClassOf inverse informs min 1 Interpretation` <br />
  Every behavior is informed by at least one interpretations.
  
* Functionality: Interpretation SubClassOf informs min 1 Behavior
  Each interpretation informs min one behavior.


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


  #### Actor performsRole Role
* Disjoint: `Actor DisjointWith Role` <br />
  Nothing can be both an actor and a role.
  
* Scoped domain: `exhibits some Role SubClassOf Actor` <br />
  Anything that performs a role must be an actor.
  
* Scoped range: `Actor SubClassOf exhibits only Role` <br />
  Anything an actor performs must be a role.
  
* Structural tautology: `Actor SubClassOf exhibits min 0 Roles` <br />
  An actor may exhibit zero or more roles.
  
* Inverse Qualified Scoped Functionality: `Role SubClassOf inverse exhibits min 1 Actor` <br />
  Every role is performed by at least one actor.


  #### Role sets Expectation
* Disjoint: `Role DisjointWith Expectation` <br />
  Nothing can be both a role and an expectation.
  
* Scoped domain: `sets some Expectation SubClassOf Role` <br />
  Anything that sets an expectation must be a role.
  
* Scoped range: `Role SubClassOf sets only Expectation` <br />
  Anything a role sets must be an expectation.
  
* Structural tautology: `Role SubClassOf sets min 0 Expectation` <br />
  An role may exhibit zero or more expectations.
  
* Inverse Qualified Scoped Functionality: `Expectation SubClassOf inverse sets min 1 Role` <br />
  Every expectaton is set by at least one role.


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
  Every observation is about at least one feature of interest.

* Qualified Scoped Functionality: `Observation SubClassOf hasFeatureOfInterest exactly 1 FeatureOfInterest` <br /> 


#### Observation observedProperty ObservableProperty

* Disjoint: `Observation DisjointWith ObservableProperty` <br />
Nothing can be both an observation and an observable property.

* Scoped Domain: `observedProperty some ObservableProperty SubClassOf Observation` <br />
Anything that has an observed property must be an observation.

* Scoped Range: `Observation SubClassOf observedProperty only ObservableProperty` <br/>
Anything an observation is about must be an observable property.

* Existential: `Observation SubClassOf observedProperty some ObservableProperty` <br />
Every observation has at least one observable property.


#### ObservationCollection hasMember Observation
* Disjoint: `Observation DisjointWith ObservationCollection` <br />
Nothing can be both an observation and an observation collection

* Scoped Domain: `hasMember some Observation SubClassOf ObservationCollection` <br />
Anything that is a member of an observed property must be an observation.

* Scoped Range: `ObservatioCollection SubClassOf hasMember only Observation` <br/>
Anything an obervation collection has as a member is an observation.

* Existential: `ObservationCollection SubClassOf hasMember some Observation` <br />
Every observation collection has at least one observation.

* Functionality: ObservationCollection SubClassOf hasMember min 1 Observation
Each observation collection has min one observation.


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


## Quantity
![QUDT module schema](../schema-diagrams/Quantity/Quantity.jpg)
### Axioms
#### Quantity hasQuantityValue QuantityValue
* Disjoint: `Quantity DisjointWith QuantityValue` <br />

* Scoped Domain: `hasQuantityValue some QuantityValue SubClassOf Quantity` <br />

* Scoped Range: `Quantity subClassOf hasQuantityValue only QuantityValue` <br />

* Existential: `Quantity SubClassOf hasQuantityValue some QuantityValue` <br />

* Qualified Scoped Functionality: `Quantity SubClassOf hasQuantityValue exactly 1 QuantityValue` <br />


#### Quantity hasQuantityKind QuantityKind
* Disjoint: `Quantity DisjointWith QuantityKind` <br />
  Nothing can be both a measured amount and a kind of quantity.
  
* Scoped domain: `hasQuantityKind some QuantityKind SubClassOf Quantity` <br />
  Anything that has a quantity kind must be a quantity.
  
* Scoped range: `Quantity SubClassOf hasQuantityKind only QuantityKind` <br />
  Anything a quantity has as its kind must be a quantity kind.
  
* Existential: `Quantity SubClassOf hasQuantityKind some QuantityKind` <br />
  Every quantity has a kind.

*  Qualified Scoped Functionality: `Quantity SubClassOf hasQuantityKind exactly 1 QuantityKind` <br />
  Every quantity has exactly one kind


#### QuantityValue hasUnit Unit

* Disjoint : `QuantityValue DisjointWith Unit` <br />

* Scoped Domain: `hasUnit some Unit SubClassOf QuantityValue` <br />

* Scoped Range: `QuantityValue SubClassOf hasUnit only Unit` <br />

* Existential: ` QuantityValue SubClassOf hasUnit some Unit` <br />

* Qualified Scoped Functionality: `QuantityValue SubClassOf hasUnit exactly 1 Unit` <br />


## Identifier

### Axioms
#### Agent hasIdentifier Identifier
* Disjoint: `Quantity DisjointWith Identifier` <br />

* Scoped Domain: `hasIdentifier some Identifier SubClassOf Agent` <br />

* Scoped Range: `Agent subClassOf hasIdentifier only Identifier` <br />

* Existential: `Agent SubClassOf hasIdentifier some Identifier` <br />

* Qualified Scoped Functionality: `Agent SubClassOf hasIdentifier exactly 1 Identifier` <br />


#### Identifier hasIdentifierType IDType
* Disjoint: `Identifier DisjointWith IDType` <br />
  Nothing can be both an identifier type and an identifier.
  
* Scoped domain: `hasIdentifierType some IDType SubClassOf Identifier` <br />
  Anything that has an identifier type must be an identifier.
  
* Scoped range: `Identifier SubClassOf hasIdentifierType only IDType` <br />
  Anything an identifier has as its type must be a identifier type.
  
* Existential: `Identifier SubClassOf hasIdentifierType some IDType` <br />
  Every identifer has a type.

*  Qualified Scoped Functionality: `Identifier SubClassOf hasIdentifierType exactly 1 IDType` <br />
  Every identifier has exactly one type




## DataTransformation

### Axioms
#### Agent hasIdentifier Identifier
* Disjoint: `Quantity DisjointWith Identifier` <br />

* Scoped Domain: `hasIdentifier some Identifier SubClassOf Agent` <br />

* Scoped Range: `Agent subClassOf hasIdentifier only Identifier` <br />

* Existential: `Agent SubClassOf hasIdentifier some Identifier` <br />

* Qualified Scoped Functionality: `Agent SubClassOf hasIdentifier exactly 1 Identifier` <br />


#### Result hasIdentifierType DataType
* Disjoint: `Result DisjointWith DataType` <br />
  Nothing can be both a DataType and a Result.

  SHOULD PROBABLY DELETE THIS ONE
* Scoped domain: `hasDataType some DataType SubClassOf Result` <br />
  Anything that has a DataType must be a Result.
  
* Scoped range: `Result SubClassOf hasDataType only DataType` <br />
  Anything a Result has as its type must be a DataType.
  
* Existential: `Result SubClassOf hasDataType some DataType` <br />
  Every Result has a type.

*  Qualified Scoped Functionality: `Result SubClassOf hasDataType exactly 1 DataType` <br />
  Every Result has exactly one type
