# SEPIO-ontology

***NOTICE:*** THE SEPIO ONTOLOGY IS IN ITS EARLY STAGES OF DEVLEOPMENT, UNDERGOING ITERATIVE REFINEMENT AS NEW REQUIREMENTS EMERGE AND ALIGNMENT WITH EXISTING STANDARDS IS EXPLORED.  WE WELCOME ANY FEEDBACK YOU MAY HAVE IN THE FORM OF USE CASES, EXEMPLAR DATA, OR REQUIREMENTS. PLEASE SUBMIT TO OUR TRACKER [HERE](https://github.com/monarch-initiative/SEPIO-ontology/issues).  

-----

### OVERVIEW 
The **Scientific Evidence and Provenance Information Ontology (SEPIO)** was developed to support description and evaluation of evidence and provenance information for scientific assertions (aka 'claims'). **Evidence** is defined as information as used to evaluate the validity of an assertion. **Provenance** information describes the process history leading to an assertion being made, including processes generating information used as evidence for the assertion, the act of interpreting this evidence information in support of the assertion, and descriptions of entities that participated in these activities. Together, evidence and provenance information serve to explain why one would believe my particular assertion to be true, and how confident one can be in its validity. 
 
SEPIO development is driven primarily by the need to represent and integrate diverse evidence and provenance metadata that is provided for  scientific claims in the context of  knowledgebases and literature. The SEPIO model is  structured to facilitate critical evaluation and comparison of scientific claims - to ultimately help us to understand how we know the things we do, why we don’t know the things we don’t, and what type of evidence is needed to firmly establish dubious claims as scientific fact.
 
### CORE CONCEPTS

The core of the SEPIO model is set of related informational entities representing **assertions**, **evidence lines**, and **evidence (supporting information)**.  These concepts are commonly referenced, implicitly or explicitly, across various formal models related to evidence and provenance for scientific claims [1,2,3,4], and are rooted in philosophical accounts of reasoning, argument, and discourse. Around these concepts, SEPIO provides a minimal but extensible model of process and process participants that are necessary to address its driving use cases and requirements (Figure 1 below). 

Definitions and examples of the core concepts in the SEPIO model. Figure 1gives a high-level view of the relationships SEPIO defines between these concepts.

**Term:** Assertion (aka Claim)  
**Definition:** A statement of purported truth, as made by a particular agent on a particular occasion.  
**Example:** The ENIGMA consortium’s assertion that BRCA1:2685T>A mutation is pathogenic for breast cancer.  
**Comments:** The identity of a particular assertion is dependent upon (1) what it claims to be true  (ie. the 'proposition' it puts forth as being true), (2) the agent asserting it, and (3) the occasion on which the assertion is made. Many agents can make assertions expressing belief in the same proposition  - e.g. ENIGMA’s assertion that that BRCA1:2685T>A is pathogenic for breast cancer is a separate instance from ClinGen's  assertion of the same underlying proposition.  Likewise, a single agent can make more than one assertion of belief in the same proposition on different occasions  - e.g. ENIGMA may make a separate assertion of the same proposition that BRCA1:2685T>A  is pathogenic for breast cancer at a later date, based on additional evidence.   
  
  
**Term:** Evidence (aka 'supporting information')  
**Definition:** A piece of information that is used to establish the validity of an assertion (or more precisely, the truth of the  proposition put forth by the assertion)    
**Example:** Any information artifact can be used as evidence, including:    
- primary research data, such as measurement values of wild-type vs mutant protein activity, or values of mutation frequency values in a population.
- statistically calculations derived from primary data, such as a p-value measuring the statistical significance of an observed phenomenon	
- artifacts summarizing research findings such as a published figure or data table. 
- assertions of purported facts as made by experts, such as the claim that loss of BRCA gene function is a causative mechanism for breast cancer (which as a scientific assertion, will have its own trail of evidence)   
**Comments:** Evidence information broadly coverings any information interpreted as evidence in evaluating an asserted proposition. Evidence is a role that such information artifacts play, as realized in the act of their interpretation toward evaluating a target assertion.  any piece of information has the potential to serve as evidence, but only become evidence information when it is used in this way.  
  
  
**Term:** Evidence Line   
**Definition:** Information artifacts that group all evidence that constitutes a single, independent argument relevant to the validity of a target assertion.    
**Example:** All information derived from a single line of investigation is grouped into a single evidence line when they speak to a single argument relevant to other validity of the target assertion. For example, a single evidence line would group primary counts, derived p-values, summary figures,  and asserted conclusions from a study on the  frequency of the BRCA1:2685T>A mutation in breast cancer patients vs healthy controls.    
**Comments:**  Information derived from separate studies or lines of reasoning may be grouped under a single evidence line in cases where they are dependent on each other to qualify as evidence  (ie. have  legitimate bearing on the probability of accepting the proposition put forth by the assertion as true).  For example, a finding that the BRCA1:2685T>A  mutation causes loss of BRCA gene function is evidence for a causative relationship between this mutation and breast cancer only if it is also true that loss of BRCA gene function is an established mechanism for breast cancer.  Information relevant to these independent facts would all be grouped under a single evidence line, because only their combination represents a meaningful argument for the proposition that BRCA1:2685T>A  is pathogenic for breast cancer.  

Evidence lines are defined with respect to a particular target assertion (i.e. an instance of an evidence line is relevant only to one asserted proposition).  In this respect, it can be helpful to think of evidence lines as the reified relationship between one or more pieces of evidence information and their target assertion.  
This relationship groups individual evidence information into discrete arguments as described above, and provides meaningful context in which to understand how individual pieces of evidence information was organized and interpreted as evidence by the asserting agent.
  
    
      
        
        



**Figure 1: The SEPIO Conceptual Model**
SEPIO provides a generic and extensible model that is capable of supporting rich but efficient descriptions of the evidence and provenance behind scientific claims.
 

![]( )

_**Figure 1**: Nodes represent core SEPIO types and give examples of each are shown in italics. Information artifacts are outlined in green, processes in orange, and process participants in blue. Cardinalities are indicated for each relationship in the model. A given **proposition** can be expressed in one or more **assertions**. **Assertions** generated by **assertion processes** performed by particular **agents** at particular locations and times, often as specified in formal **assertion protocols**. The **assertion process** also generates one or more **lines of evidence**, as a result of the agent's interpretation of **supporting data** as evidence for or against a **proposition**. **Supporting data** is generated through **data generating processes**, performed by particular **agents** at particular locations and times, using various types of **resources**, and applying various types of **techniques**._

The following **Wiki pages** provide additional information about the SEPIO ontology and its support for structuring evidence and provenance metadata around scientific claims. 

1. [Core Concepts and Relationships](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Core-Concepts-and-Relationships)
2. [Use Cases and Requirements](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Use-Cases-and-Requirements)
3. [Real Data Examples](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Real-Data-Examples)
4. [Ontological Commitments](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Ontological-Committments)



### References

1. **The Semantic EvidencE (SEE) Framework**: Bölling, Christian, Michael Weidlich, and Hermann-Georg Holzhütter. "SEE: structured representation of scientific evidence in the biomedical domain using Semantic Web techniques." Journal of biomedical semantics 5.1 (2014)
2. **The Micropublications Model (MP)**: Clark, Tim, Paolo N. Ciccarese, and Carole A. Goble. "Micropublications: a semantic model for claims, evidence, arguments and annotations in biomedical communications." Journal of biomedical semantics 5.1 (2014)
3. **Open Biomedical Annotations (OBAN)**: Sarntivijai, Sirarat, et al. "Linking rare and common disease: mapping clinical disease-phenotypes to ontologies in therapeutic target validation."
4. **The Evidence Code Ontology (ECO)**: Chibucos, Marcus C., et al. "Standardized description of scientific evidence using the Evidence Ontology (ECO)." Database 2014 (2014)
