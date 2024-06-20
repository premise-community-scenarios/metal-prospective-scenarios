# Prospective life cycle assessment of metals supply for the energy transition
This repository contains the code and data from my master project on the prospective life 
cycle assessment of metals supply for the energy transition. The project aimed to assess 
the environmental impacts associated with the production of metals needed in renewable 
technologies. The Premise library was used to generate prospective ecoinvent databases 
according to the results of the integrated assessment model REMIND. A custom scenario 
was created using Premise to model the evolution of secondary production in the supply 
of aluminum, copper, cobalt, nickel and lithium. The evolution of the electricity mix 
and the efficiency of aluminum smelters in China were also modeled.

**The scenario is to be used in combination with REMIND global scenarios only.**

# Requirements

- ecoinvent 3.10 cutoff

# Use

```python

    from premise import NewDatabase
    from datapackage import Package
    
    external_scenarios = [
        {"scenario": "SPS", "data": Package("./datapackage.json")},
    ]
    
    scenarios = [
        {"model": "remind", "pathway":"SSP2-PkBudg500", "year": 2030, "external scenarios": external_scenarios},
        {"model": "remind", "pathway":"SSP2-PkBudg500", "year": 2040, "external scenarios": external_scenarios},
        {"model": "remind", "pathway":"SSP2-PkBudg500", "year": 2050, "external scenarios": external_scenarios},
    ]
    
    
    ndb = NewDatabase(
            scenarios = scenarios,        
            source_db="ecoinvent-3.10-cutoff",
            source_version="3.10",
            key='tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo=',
            biosphere_name="ecoinvent-3.10-biosphere",
    )
    ndb.update("external")

```



# Author
Marguerite Fauroux, margueritefauroux@gmail.com

# Original repository
https://github.com/margueritefauroux/pLCA_metals

# License
Missing
