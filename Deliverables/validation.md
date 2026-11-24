\# Validation



\## Competency Question Name

\*\*Competency Question:\*\* "What physiological measures is a device capable of collecting?"







\*\*SPARQL Query:\*\*

```

SELECT DISTINCT ?measure

WHERE {

&#x20; ?measure a o:PhysiologicalMeasure .

}

ORDER BY ?measure```



\*\*Results:\*\*

| measure |

| :----: |

| HeartRate |

| HeartRateVariability |

| RespiratoryRate |

| SpO2 |

| Stress |



\## Competency Question Name

\*\*Competency Question:\*\* "What specific survey(s) did an agent(SUB7) answer??"





\*\*SPARQL Query:\*\*

```

SELECT DISTINCT ?survey

WHERE {

&#x20; ?response o:providedBy ?subject ;

&#x20;           o:answers ?item .

&#x20; ?survey o:hasItem ?item .

&#x20; FILTER (STRAFTER(STR(?subject), "/actor/") = "SUB7")

}

ORDER BY ?survey```



\*\*Results:\*\*

| survey |

| :----: |

| Fatigue |

| FlowScale |

| NASA\_TLX |



\## Competency Question Name

\*\*Competency Question:\*\* "What wearable(s) did the agent wear?"





\*\*SPARQL Query:\*\*

```

SELECT DISTINCT ?wearable

WHERE {

&#x20; ?subject o:wears ?wearable .

&#x20; FILTER (STRAFTER(STR(?subject), "/actor/") = "SUB7")

}

```



\*\*Results:\*\*

| wearable |

| :----: |

| GarminWatch |



