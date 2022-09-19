# System Scope and Context

> The context which delimits the system from its (external) communication partners (neighboring systems and users). It specifies or documents the external interfaces. You should always document the context from a business or domain perspective. If infrastructure or specific hardware plays an important role, you might also show a technical perspective.

## Business Context

**Diagram or Table**

```mermaid
C4Context
  title Machine Learning Solution Context (Mermaid)
  
  Person(client1, "First User")
  Person(client2, "Second User")
  System(system, "ML System")

  Rel(client1, system, "API call")
  Rel(client2, system, "API call")
```

```plantuml
@startuml
!include <C4/C4_Container>

title Machine Learning Solution Context (PlantUML)

Person(client1, "First User")
Person(client2, "Second User")
System(system, "ML System")

Rel(client1, system, "API call")
Rel(client2, system, "API call")
@enduml
```

**optionally: Explanation of external domain interfaces**

## Technical Context

```mermaid
C4Context
  title Machine Learning Solution
  System_Ext(client1, "Webshop Frontend")
  System_Ext(client2, "Demo UI")

  Container_Boundary(system, "ML System") {
    System(api, "Model serving API")
    System(train, "Model Training")
    System(ingestion, "Data Ingestion")
  }
  SystemDb_Ext(db, "Ordering system DB")

  Rel(client1, api, "API call")
  Rel(client2, api, "API call")
  Rel(train, api, "model")
  Rel(ingestion, train, "data")
  Rel(ingestion, db, "fetch data")
```

**Diagram or Table**

**optionally: Explanation of technical interfaces**

**Mapping Input/Output to Channels**
