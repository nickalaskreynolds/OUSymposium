OU Symposium Slide Notes
========================


General Format
--------------

- 5 minute overview/background of our science
- 5 minutes on our specific research
- 5 minutes on our general computation need
- 5 minutes on our specific analysis in relation to computation and what is our specific needs for computers
- 5 minutes for results and greater impacts
- 5 minutes for questions



Table of Contents
-----------------
- title slide: First Look at Protostars: High Fidelity Modeling and the Youngest of Stars with OSCER
- collaboration: VANDAM, HOPS, misc
- motivation
    - questions we try to answer are generally: where did we come from, what else is out there, and where are we going to end up?
    - questions we (specifically) answer: Where did we come from, how did we get here, what else is out there, and are we unique

(not everyone is an astronomer much less expert of star/planet formation)

- background on star formation
    - evolution of stars: MC -> Protostar -> Main Sequence (star) -> Giants -> WD/NS/BH -> MC ...
        - What determines the specific track: to first order mass
        - whats interesting is once you hit MS, the only thing that matters (to first order) is mass
        - what determines MS and single/multiple star. 
        - what about planets? Gas is gone so gas giant formation not possible at MS
    - Look at Cloud -> Class III
        - evolution
        - when does gas leave?
    - pictures of orion/perseus HST
    - these are optically thick....big problem
        - interesting, opacity is related to frequency so just go to longer wavelengths: IR/RADIO
- Instruments
    - problem, resolution is also frequency dependent theta = lambda/size
        - so now we need large telescopes. We want <10AU scales and stuff is away so we need 0.1'' resolution
        - similar to saying 1/1000 of your fingernail width at arms length away from your eye.
        - which means we need telescopes on order of the size of km at least...
        - not doable
    - interferometry
        - lots of smaller telescopes across several miles acts like 1 big telescope(with limitations)
    - fixed our problems
        - alma, vla, noema, carma
    - so what kind of data do we get?
        - photometry
            - just like a camera from your cellphone we can get an image
            - if we do this a lot we get the energy distribution of objet
        - spectroscopy
            - this gives us color, not just 3 color but thousands. Gives us information of atoms, molecules
        - we get both simultaneously
    - so to summarize we went from HST -> ALMA
        - now we can look at the systems themselves and not just the environment or nulk properties
        - from these we can get stellar mass, disk mass, size, speeds, molecular abundance, temperatures, geometries, multiplicities, etc
- Computation
    - parameters
        - we now have 20-40 parameters to fit with a lot of degeneracy
        - turning into a computation problem
        - we want to make a model, fit this model to the data, and then get the model parameters
        - sounds like a great problem for parallelization and MCMC
    - so now our problem is one of scalability
        - we want to reach numerical convergence of the models and statistical convergence of the model parameter sets
        - insert EMCEE,openmpi, pdspy
        - insert slide about scalability
    - computation requirements
        - generally models take 60k core-hours for a single system
            - we have a few hundred of these
        - our systems
            - 2x 28 physical core
            - so while good not enough (months of convergence)
        - into oscer
            - generally we ask for 5-15 nodes x 20 core x 48 hours x 15-5 separate runs x systems
            - some take more and some take less depending on complexity, how quickly they converge, etc
        - currently not GPU ready so we just want max CPU core hours
    - we are requesting a lot but why again?
- impacts and fundamentals
    - we are trying to understand our universse and namely understand how did we form and what other things form in the universe
    - are we unique?
    - where/when/how do planets form and same for stars.
    - how do we get the tichness of chemicals
    - we want to answer these in a statistically significant way too so that means large observational surveys, lots of models
    - our group at OU + collaborations around the world are the forerunners of this field
- thanks
    - none of this would happen without OSCER, OU, NSF, and the collaborators
    - special thanks to Henry, Horst, Oscer IT, and CAS IT

