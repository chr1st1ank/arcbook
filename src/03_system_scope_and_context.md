# System Scope and Context

## Business Context

**\<Diagram or Table>**

**\<optionally: Explanation of external domain interfaces>**

## Technical Context


```mermaid
C4Context
  title Machine Learning Solution
  Person(client1, "First User")
  Person(client2, "Second User")
  Container_Boundary(system, "ML System") {
    System(api, "Model serving API")
    System(train, "Model Training")
    System(ingestion, "Data Ingestion")
  }
  SystemDb_Ext(db, "Ordering system DB")

  BiRel(client1, api, "API call")
  BiRel(client2, api, "API call")
  Rel(train, api, "model")
  Rel(ingestion, train, "data")
  Rel(ingestion, db, "fetch data")
```


```mermaid
stateDiagram-v2
    [*] --> Still
    Still --> [*]
    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
            
```

**\<Diagram or Table>**

**\<optionally: Explanation of technical interfaces>**

**\<Mapping Input/Output to Channels>**
