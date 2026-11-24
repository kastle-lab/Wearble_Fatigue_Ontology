# Validation

## CQ1: Physiological measures a device can collect

**Competency Question:** "What physiological measures is a device capable of collecting?"

**SPARQL Query:**

```sparql
PREFIX o: <http://www.semanticweb.org/user/ontologies/2026/10/>

SELECT DISTINCT ?measure
WHERE {
  ?measure a o:PhysiologicalMeasure .
}
ORDER BY ?measure
```

**Results:**

| measure              |
| :------------------: |
| HeartRate            |
| HeartRateVariability |
| RespiratoryRate      |
| SpO2                 |
| Stress               |

## CQ2: Surveys answered by an agent

**Competency Question:** "What specific survey(s) did an agent (SUB7) answer?"

**SPARQL Query:**

```sparql
PREFIX o: <http://www.semanticweb.org/user/ontologies/2026/10/>

SELECT DISTINCT ?survey
WHERE {
  ?response o:providedBy ?subject ;
            o:answers ?item .
  ?survey o:hasItem ?item .
  FILTER (STRAFTER(STR(?subject), "/actor/") = "SUB7")
}
ORDER BY ?survey
```

**Results:**

| survey    |
| :-------: |
| Fatigue   |
| FlowScale |
| NASA_TLX  |

## CQ3: Wearables worn by an agent

**Competency Question:** "What wearable(s) did the agent (SUB7) wear?"

**SPARQL Query:**

```sparql
PREFIX o: <http://www.semanticweb.org/user/ontologies/2026/10/>

SELECT DISTINCT ?wearable
WHERE {
  ?subject o:wears ?wearable .
  FILTER (STRAFTER(STR(?subject), "/actor/") = "SUB7")
}
```

**Results:**

| wearable    |
| :---------: |
| GarminWatch |
