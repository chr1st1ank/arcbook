# Quality Requirements

> Quality requirements, often described as scenarios. You may use a quality tree to provide a high-level overview. The most important quality goals should have been already described in section 1.2. (quality).
> 
> https://docs.arc42.org/section-10/

```mermaid
%%{init: { "flowchart": { "curve": "linear"} } }%%
graph LR
    sys(ISO 25010 Software product quality)

    sys --- suitability(Functional Suitability)
    sys --- reliability(Reliability)
    sys --- efficiency(Performance Efficiency)
    sys --- useability(Useability)
    sys --- security(Security)
    sys --- compatibility(Compatibility)
    sys --- maintainability(Maintainability)
    sys --- portability(Portability)

    suitability --- appropriateness(Appropriateness)
    suitability --- correctness(Correctness)
    suitability --- completeness(Completeness)

    reliability --- availability(Availability)
    reliability --- fault-tolerance(Fault tolerance)
    reliability --- recoverability(Recoverability)

    efficiency --- time(Time behaviour)
    efficiency --- resource(Resource utilization)
    efficiency --- capacity(Capacity)

    useability --- recogniseability(Appropriateness recogniseability)
    useability --- learnability(Learnability)
    useability --- ease(Ease-of-use)
    useability --- user-error-protection(User error protection)
    useability --- attractiveness(Attractiveness)
    useability --- accessibility(Technical accessibility)

    security --- confidentiality(Confidentiality)
    security --- integrity(Integrity)
    security --- non-repudiation(Non-repudiation)
    security --- accountability(Accountability)
    security --- authenticity(Authenticity)

    compatibility --- coexistence(Coexistence)
    compatibility --- interoperability(Interoperability)

    maintainability --- modularity(Modularity)
    maintainability --- reuseability(Reuseability)
    maintainability --- analyzability(Analyzability)
    maintainability --- changeability(Changeability)
    maintainability --- testability(Testability)

    portability --- adaptability(Adaptability)
    portability --- installability(Installability)
    portability --- replaceability(Replaceability)
```
*Software product quality as defined in ISO 25010.*

## Quality Tree

```mermaid
graph TD
    sys(System Quality Requirements)

    sys --- suitability(" Functional Suitability")
    sys --- reliability(Reliability)
    sys --- efficiency(Performance Efficiency)
    sys --- useability(Useability)
    sys --- security(Security)
    sys --- compatibility(Compatibility)
    sys --- maintainability(Maintainability)
    sys --- transferability(Transferability)

    suitability --- acc("🎯 Accurate predictions")
    reliability --- av("🏃‍♂️ High Availability")
```


## Quality Scenarios

### Accurate Predictions
Predictions on typical user data achieve an accuracy of at least 60%.
- **Quality Aspect**: Functional Suitability
- **Trigger**: 
- **Reaction**:
- **Result**:

