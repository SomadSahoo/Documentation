
=================
Terminology
=================

Last updated: October 18, 2023, Yilin Huang, Delft University of
Technology

This document provides an overview of the terminology used in the MMviB
project. The listed terms primarily consist of those commonly used and
defined in simulation modelling literature. Some terms are new and
specific to MMviB. These are derived from literature and based on common
modelling practices, if applicable, and are the outcomes of
collaborative design and development within the project.

`List of Terms in
Thematic <#list-of-terms-in-thematic>`__

`Strategic, Tactical, and Operational
goals <#strategic-tactical-and-operational-goals>`__\ 

`Model, Simulation model, and Calculation
model <#model-simulation-model-and-calculation-model>`__\ 

`Distributed
simulation <#distributed-simulation>`__\ 

`Source system <#source-system>`__\ 

`Abstraction <#abstraction>`__\ 

`Scope and Scale <#scope-and-scale>`__\ 

`Granularity and
Resolution <#granularity-and-resolution>`__\ 

`Model parameters and Model
inputs <#model-parameters-and-model-inputs>`__\ 

`Static data and Dynamic
data <#static-data-and-dynamic-data>`__\ 

`Multi-model and
Multi-modelling <#multi-model-and-multi-modelling>`__\ 

`Multi-model
infrastructure <#multi-model-infrastructure>`__\ 

`Multi-model
constitution <#multi-model-constitution>`__\ 

`Multi-model experimental
setup <#multi-model-experimental-setup>`__\ 

`Multi-model
workflow <#multi-model-workflow>`__\ 

`Multi-model
configuration <#multi-model-configuration>`__\ 
`Workflow task and Model
adapter <#workflow-task-and-model-adapter>`__\ 

`Model orchestrator and Model
orchestration <#model-orchestrator-and-model-orchestration>`__\ 

`Model verification and Model
validation <#model-verification-and-model-validation>`__\ 

`Scenario and Scenario
space <#scenario-and-scenario-space>`__\ 

`Experiment, Experimentation and Experimental
frame <#experiment-experimentation-and-experimental-frame>`__\ 

`Uncertainty
analysis <#uncertainty-analysis>`__\ 

`List of Terms in Alphabetical
order <#list-of-terms-in-alphabetical-order>`__\ 

List of Terms in Thematic 
=========================

Strategic, Tactical, and Operational goals 
------------------------------------------

+----------------+--------------------------+-------------+----------+
|                | **Main Question**        | **Planning  |          |
|                |                          | Horizon**   | **Scope**|
+================+==========================+=============+==========+
| Strategic      | What do we want          | Long-term   | Broadest |
| goals          |                          |             |          |
+----------------+--------------------------+-------------+----------+
| Tactical goals | How do we approach this  | Medium-term | Medium   |
+----------------+--------------------------+-------------+----------+
| Operational    | How do we plan           | Short-term  | Least    |
| goals          | day-to-day operations    |             | broad    |
+----------------+--------------------------+-------------+----------+

Strategic goals have a long-term planning horizon. They deal with the
main question of “what do we want”. These goals have the broadest scope
compared to tactical and operational goals. In terms of cascading
effect, strategic plans are cascaded to tactical plans, and subsequently
to operational plans.

Tactical goals have a medium-term planning horizon. They deal with the
main question of “how do we approach this” where *this* refers to a
given strategic goal.

Operational goals have a short-term planning horizon. They deal with the
main question of “how do we plan day-to-day operations”. In terms of
scope, these goals are the least broad. The achievement of operational
goals leads to the achievement of tactical goals, which leads to the
achievement of strategic goals.

Model, Simulation model, and Calculation model
----------------------------------------------

A model is an abstraction of a system intended to replicate some
properties of that system. This means that a model needs to possess
three features. (1) Mapping feature. A model is based on an original
system, existing or non-existing. We may call the original system a
source system or a referent. (2) Reduction feature. A model only
reflects a relevant selection of an original system’s properties. (3)
Pragmatic feature. A model needs to be usable in place of an original
system with respect to some purpose.

A (computational) simulation model is a piece of software that has a set
of instructions that defines rules and constraints, among others, for
generating input-to-output (I/O) behaviour of the model.

Simulation is often used to imitate the operation of a real system by
executing a model of that system over time. In this case, the model is
executed (a.k.a. simulated) iteratively with changing model states by
advancing a time axis (a.k.a. time-stepping). Simulation models of this
kind are dynamic, as opposed to static models, which do not simulate
systems change over time. A (computational) static model is not computed
with time-stepping.

A calculation model refers to a computational model that makes numerical
calculations. A calculation model is a static model.

Distributed simulation 
----------------------

Distributed simulation is executed on distributed computer systems,
namely systems composed of multiple interconnected computers.

Source system 
-------------

A source system is also known as an original system, a target system, a
system referent, a system of interest, etc. It refers to any system that
is under modelling interest. This can be, for example, a natural system,
an engineered system, a social system, etc., and a combination of any of
these systems.

Abstraction 
-----------

Abstraction is a process of modelling that focuses on a source system
and simplifies it by selecting a set of quantities and relationships
that represent that source system given a modelling purpose. The
validity of an abstraction is considered in relation to the modelling
purpose and the experimental frame of a model.

Scope and Scale
---------------

Scope refers to the fact that a modelled set of diverse elements or
concepts is a (selected) subset of those in a source system. This
modelled set of elements or concepts can represent various aspects,
phenomena, ideas, or any subject matters in a source system that deemed
relevant given a modelling purpose.

For example, a wind farm model or a solar farm model can have a scope
that includes energy, heat, electricity, economics, finances, and
weather conditions. Furthermore, the model may or may not include the
change of weather conditions. In this case, we say that the change of
weather conditions is within or out of the scope of the model.

Scale is the range (or sometimes extent or dimension) of the elements or
concepts of a model representing a source system.

Scale, in general, implies a mapping relation from a model to its source
system. The latter characterizes the range, extent or dimension captured
by the model given a modelling purpose.

For example, a wind farm model may simulate the wind energy generation
from all wind farms in the Netherlands for the next 10 years. In this
case, we say that the geographical (or spatial) scale of the model is
the Netherlands, and the time scale of the model is 10 years.

Scale is often deemed as being temporal or spatial, but it is not
limited to these two types. It also can be defined with respect to
objects, processes, or any other subject matters in a source system. For
example, a model of a biological system may be at a scale of cell,
tissue, organ or beyond.

Granularity and Resolution 
--------------------------

Granularity refers to the level of details at which a model represents a
source system. It is a property belongs to a model, and is often
reflected by the number of variables, and the complexity of the
relations of variables in the model.

Example 1: a wind farm model that simulates wind energy generation of
all wind farms in the Netherlands, may represent each wind farm
individually with different characteristics. In this case, the
granularity of this model is higher or finer than a model that would
represent all Dutch wind farms in an aggregated manner.

Example 2: a wind farm model that simulates wind energy generation for
the next 10 years may calculate energy generation at yearly, monthly,
weekly, daily, or hourly intervals. These are different temporal
granularities on a time scale of 10 years.

Granularity can be *structural* (a.k.a. compositional) or *atomic*.
Structural (or compositional) granularity is characterized by the number
of model components and their relations within a *composite* model.
Atomic granularity is characterized by the information details, i.e.,
the number of variables and their relations, within a
*non-compositional* model.

Resolution typically refers to atomic (non-compositional) granularity,
a.k.a. data granularity or data resolution.

Model parameters and Model inputs 
---------------------------------

Model parameters are constants that define the relationships among the
variables in a model. Once set, the value of a model parameter does not
change during one simulation run.

“\ *The distinction between these [variables and parameters] is not
always clear cut, and it frequently depends on the context in which the
variables appear. Usually a model is designed to explain the
relationships that exist among quantities which can be measured
independently in an experiment; these are the variables of the model. To
formulate these relationships, however, one frequently introduces
‘constants’ which stand for inherent properties of nature (or of the
materials and equipment used in a given experiment). These are the
parameters.*\ ” Bard, Yonathan (1974). Nonlinear Parameter Estimation.
New York: Academic Press. p.11.

For example, consider a simple model y=f(x) where f(x)=ax+b. Commonly
known, x is the model input variable, y is the model output variable.
The function f(x) defines the input-to-output relation in which a and b
are the (constant) model parameters.

The term of model inputs is often used loosely. It may refer to model
input variables, model input data, or both. Model input variables refer
to a model’s independent variables. Model input data are used to
configure a model’s independent variables and sometimes also model
parameters.

In MMviB, model inputs can consist of static data and dynamic data.

Static data and Dynamic data
----------------------------

Static data are used to configure the independent variables, sometimes
also parameters, in a model. They typically determine the boundary
conditions and other initial conditions of a model. For instance, the
placement of buildings, cables, and pipelines.

Static data are used for model configuration before the start of a
simulation run. They are not used for model configuration during a
simulation run.

Dynamic data are generated by the single (stand-alone) models in a
multi-model workflow. In the MMviB project, both the (intermediate)
outputs of the single models, and the (final) outputs of a multi-model,
are deemed as dynamic data.

Note that dynamic output data of a single model often becomes dynamic
input data of another (coupled) single model in a multi-model workflow.
Dynamic data does not exist before a simulation run.

Multi-model and Multi-modelling
-------------------------------

In MMviB, a multi-model is an (ensemble) model that consists of two or
more single (independent) models that can interoperate to produce
meaningful experimental outputs given a predefined modelling purpose.

In MMviB, multi-modelling refers to multi-model constitution as well as
multi-model experimentation.

Multi-model infrastructure
--------------------------

In MMviB, multi-model infrastructure refers to all facilitating services
(including software and methods) that enable multi-modelling. The
multi-model infrastructure does not include the individual independent
models themselves.

Multi-model constitution 
------------------------

In MMviB, multi-model constitution refers to design-time processes (and
activities) of multi-model composition (including the workflow design)
prior to multi-model experimentation.

This includes, e.g., the selection of plausible single models, the
definition of data exchange methods and sequences, the adaptation
required thereof, among others, with respect to a given modelling
purpose.

Multi-model experimental setup 
------------------------------

A multi-model experimental setup describes what is required to conduct a
multi-model experiment. It consists of (1) a multi-model workflow (and
workflow parameters), and (2) a multi-model configuration.

Multi-model workflow 
--------------------

A multi-model workflow defines a sequence of tasks (and thereby the
sequence of individual model runs and the corresponding dynamic data
flow) through which a multi-model experiment can be conducted from
initialization to completion.

Multi-model configuration 
-------------------------

A multi-model configuration defines a set of data (via static data) to
set up a multi-model experiment, with respect to an experimental goal. A
multi-model configuration is associated to a given multi-model workflow.

Workflow task and Model adapter
-------------------------------

In MMviB, a workflow task calls a model (run), via a model adapter, and
(if applicable) passes on references to model inputs. An orchestrator
calls a workflow task and waits for the model run to be completed and
collects a reference to the corresponding model output (i.e., dynamic
data).

In MMviB, a model adapter is designed for a specific model with respect
to model orchestration. A model adapter is responsible for the
configuration and execution of a model run, and for collecting the
corresponding model output.

A multi-model workflow task calls a model adapter, providing references
to model inputs.

Model orchestrator and Model orchestration
------------------------------------------

In MMviB, a model orchestrator is responsible for model orchestration.
An orchestrator controls a multi-model workflow that runs defined
workflow tasks.

In MMviB, model orchestration refers to the overall management and
automation of a multi-model experiment.

Model verification and Model validation
---------------------------------------

Model verification addresses the main question of “Did we build the
model right?” It is the process of determining if an implemented model
is consistent with the model specification.

Model validation addresses the main question of “Did we build the right
model?” It is the process of establishing that the behaviours of the
model and the source system agree in the frame in question,
corresponding to the modelling purposes and the experimental frame.

Scenario and Scenario space
---------------------------

In general, a scenario is the description of one (possible) situation
(including actions, events, etc.) that exists or could exist (in the
past, at present, or in the future). In modelling and simulation, we
refer to a single (configured) model setting as a modelling scenario.
Ideally, a simulation scenario (definition) is platform- and
model-independent. This means one scenario may be simulated by different
models, each of which may have a platform- and model-specific setting
that is necessary to run the experiments specific to that model.

For example, the four scenarios in the *II3050* scenario space are the
*Europese, Internationale, Nationale, and Regionale sturing* (in Dutch),
each of which specifies a projection for future gas and electricity
price profiles. An individual scenario goal might therefore be to
identify the influence of the different price profiles on energy usage.

A scenario space consists of a (often large) set of scenarios that are
guided by a modelling goal. An individual scenario goal is informed by a
distinct set of (past, current, and/or future) ideals, conditions,
and/or constraints, among others.

For example, the *II3050* scenario space contains a set of four
scenarios that provide a range of projections for future energy prices.

Experiment, Experimentation and Experimental frame
--------------------------------------------------

In general, a (scientific) experiment is a procedure that is driven by
an experimental goal, to make a discovery, test a hypothesis, or
demonstrate a known fact. A simulation experiment serves the same
purpose, with a model in place of the real system.

In MMviB, a (simulation) experimental goal guides one multi-model
experimental setup as well as the selection of (multi-model) output
metrics and KPIs.

An experimental goal can be, e.g., to calculate the gas and electricity
usage given the price profile specified by a scenario. One scenario can
form a basis for multiple experiments, e.g., with different (multi-)
model configurations. This means one simulation scenario can have
multiple simulation experiments.

In modelling and simulation, one experiment refers to one (multi-) model
run (a.k.a., one simulation run) of a deterministic model, or
replication runs (a.k.a. replications, i.e., repeated runs with random
seeds) in case of a stochastic model, where the model has fixed
configuration of parameter setting and input settings. This means an
experiment is scenario-and-model specific.

Experimentation is a general term that refers to *conducting
experiments* in a collective sense. It is the activity of conducting
different experiments driven by different experimental goals.

An experimental frame is a term used initially by Zeigler (1976) to
formally describe a model’s context with the goal of providing
reproducible experiment descriptions. It specifies the conditions under
which the modelled system is observed and experimented with.

Uncertainty analysis 
--------------------

Uncertainty analysis in modelling and simulation refers to the process
of understanding how uncertainty in model parameters, model input and
model structure affect the model output.

List of Terms in Alphabetical order 
===================================

+--------------+-------------------------------------------------------+
| Abstraction  | Abstraction is a process of modelling that focuses on |
|              | a source system and simplifies it by selecting a set  |
|              | of quantities and relationships that represent that   |
|              | source system given a modelling purpose. The validity |
|              | of an abstraction is considered in relation to the    |
|              | modelling purpose and the experimental frame of a     |
|              | model.                                                |
+--------------+-------------------------------------------------------+
| Calculation  | A calculation model refers to a computational model   |
| model        | that makes numerical calculations. A calculation      |
|              | model is a static model.                              |
+--------------+-------------------------------------------------------+
| Distributed  | Distributed simulation is executed on distributed     |
| simulation   | computer systems, namely systems composed of multiple |
|              | interconnected computers.                             |
+--------------+-------------------------------------------------------+
| Dynamic data | Dynamic data are generated by the single              |
|              | (stand-alone) models in a multi-model workflow. In    |
|              | the MMviB project, both the (intermediate) outputs of |
|              | the single models, and the (final) outputs of a       |
|              | multi-model, are deemed as dynamic data.              |
|              |                                                       |
|              | Note that dynamic output data of a single model often |
|              | becomes dynamic input data of another (coupled)       |
|              | single model in a multi-model workflow. Dynamic data  |
|              | does not exist before a simulation run.               |
+--------------+-------------------------------------------------------+
| Experiment   | In general, a (scientific) experiment is a procedure  |
|              | that is driven by an experimental goal, to make a     |
|              | discovery, test a hypothesis, or demonstrate a known  |
|              | fact. A simulation experiment serves the same         |
|              | purpose, with a model in place of the real system.    |
|              |                                                       |
|              | In MMviB, a (simulation) experimental goal guides one |
|              | multi-model experimental setup as well as the         |
|              | selection of (multi-model) output metrics and KPIs.   |
|              |                                                       |
|              | An experimental goal can be, e.g., to calculate the   |
|              | gas and electricity usage given the price profile     |
|              | specified by a scenario. One scenario can form a      |
|              | basis for multiple experiments, e.g., with different  |
|              | (multi-) model configurations. This means one         |
|              | simulation scenario can have multiple simulation      |
|              | experiments.                                          |
|              |                                                       |
|              | In modelling and simulation, one experiment refers to |
|              | one (multi-) model run (a.k.a., one simulation run)   |
|              | of a deterministic model, or replication runs (a.k.a. |
|              | replications, i.e., repeated runs with random seeds)  |
|              | in case of a stochastic model, where the model has    |
|              | fixed configuration of parameter setting and input    |
|              | settings. This means an experiment is                 |
|              | scenario-and-model specific.                          |
+--------------+-------------------------------------------------------+
| Experimental | An experimental frame is a term used initially by     |
| frame        | Zeigler (1976) to formally describe a model’s context |
|              | with the goal of providing reproducible experiment    |
|              | descriptions. It specifies the conditions under which |
|              | the modelled system is observed and experimented      |
|              | with.                                                 |
+--------------+-------------------------------------------------------+
| Exp          | Experimentation is a general term that refers to      |
| erimentation | *conducting experiments* in a collective sense. It is |
|              | the activity of conducting different experiments      |
|              | driven by different experimental goals.               |
+--------------+-------------------------------------------------------+
| Granularity  | Granularity refers to the level of details at which a |
|              | model represents a source system. It is a property    |
|              | belongs to a model, and is often reflected by the     |
|              | number of variables, and the complexity of the        |
|              | relations of variables in the model.                  |
|              |                                                       |
|              | Example 1: a wind farm model that simulates wind      |
|              | energy generation of all wind farms in the            |
|              | Netherlands, may represent each wind farm             |
|              | individually with different characteristics. In this  |
|              | case, the granularity of this model is higher or      |
|              | finer than a model that would represent all Dutch     |
|              | wind farms in an aggregated manner.                   |
|              |                                                       |
|              | Example 2: a wind farm model that simulates wind      |
|              | energy generation for the next 10 years may calculate |
|              | energy generation at yearly, monthly, weekly, daily,  |
|              | or hourly intervals. These are different temporal     |
|              | granularities on a time scale of 10 years.            |
|              |                                                       |
|              | Granularity can be *structural* (a.k.a.               |
|              | compositional) or *atomic*. Structural (or            |
|              | compositional) granularity is characterized by the    |
|              | number of model components and their relations within |
|              | a *composite* model. Atomic granularity is            |
|              | characterized by the information details, i.e., the   |
|              | number of variables and their relations, within a     |
|              | *non-compositional* model.                            |
+--------------+-------------------------------------------------------+
| Model        | In MMviB, a model adapter is designed for a specific  |
| adapter      | model with respect to model orchestration. A model    |
|              | adapter is responsible for the configuration and      |
|              | execution of a model run, and for collecting the      |
|              | corresponding model output.                           |
|              |                                                       |
|              | A multi-model workflow task calls a model adapter,    |
|              | providing references to model inputs.                 |
+--------------+-------------------------------------------------------+
| Model inputs | The term of model inputs is used loosely by modelling |
|              | practitioners. It may refer to model input variables, |
|              | model input data, or both.                            |
|              |                                                       |
|              | Model input variables refer to a model’s independent  |
|              | variables.                                            |
|              |                                                       |
|              | Model input data are used to configure a model’s      |
|              | independent variables and sometimes also model        |
|              | parameters.                                           |
|              |                                                       |
|              | In MMviB, model inputs can consist of static data and |
|              | dynamic data.                                         |
+--------------+-------------------------------------------------------+
| Model        | In MMviB, model orchestration refers to the overall   |
| o            | management and automation of a multi-model            |
| rchestration | experiment.                                           |
+--------------+-------------------------------------------------------+
| Model        | In MMviB, a model orchestrator is responsible for     |
| orchestrator | model orchestration. An orchestrator controls a       |
|              | multi-model workflow that runs defined workflow       |
|              | tasks.                                                |
+--------------+-------------------------------------------------------+
| Model        | Model parameters are constants that define the        |
| parameters   | relationships among the variables in a model. Once    |
|              | set, the value of a model parameter does not change   |
|              | during one simulation run.                            |
|              |                                                       |
|              | “\ *The distinction between these [variables and      |
|              | parameters] is not always clear cut, and it           |
|              | frequently depends on the context in which the        |
|              | variables appear. Usually a model is designed to      |
|              | explain the relationships that exist among quantities |
|              | which can be measured independently in an experiment; |
|              | these are the variables of the model. To formulate    |
|              | these relationships, however, one frequently          |
|              | introduces ‘constants’ which stand for inherent       |
|              | properties of nature (or of the materials and         |
|              | equipment used in a given experiment). These are the  |
|              | parameters.*\ ” Bard, Yonathan (1974). Nonlinear      |
|              | Parameter Estimation. New York: Academic Press. p.11. |
|              |                                                       |
|              | For example, consider a simple model y=f(x) where     |
|              | f(x)=ax+b. Commonly known, x is the model input       |
|              | variable, y is the model output variable. Function    |
|              | f(x) defines the input-to-output relation in which a  |
|              | and b are the (constant) model parameters.            |
+--------------+-------------------------------------------------------+
| Model        | Model validation addresses the main question of “Did  |
| validation   | we build the right model?” It is the process of       |
|              | establishing that the behaviours of the model and the |
|              | source system agree in the frame in question,         |
|              | corresponding to the modelling purposes and the       |
|              | experimental frame.                                   |
+--------------+-------------------------------------------------------+
| Model        | Model verification addresses the main question of     |
| verification | “Did we build the model right?” It is the process of  |
|              | determining if an implemented model is consistent     |
|              | with the model specification.                         |
+--------------+-------------------------------------------------------+
| Model        | A model is an abstraction of a system intended to     |
|              | replicate some properties of that system. This means  |
|              | that a model needs to possess three features. (1)     |
|              | Mapping feature. A model is based on an original      |
|              | system, existing or non-existing. We may call the     |
|              | original system a source system or a referent. (2)    |
|              | Reduction feature. A model only reflects a relevant   |
|              | selection of an original system’s properties. (3)     |
|              | Pragmatic feature. A model needs to be usable in      |
|              | place of an original system with respect to some      |
|              | purpose.                                              |
+--------------+-------------------------------------------------------+
| Multi-model  | A multi-model configuration defines a set of data     |
| c            | (via static data) to set up a multi-model experiment, |
| onfiguration | with respect to an experimental goal. A multi-model   |
|              | configuration is associated to a given multi-model    |
|              | workflow.                                             |
+--------------+-------------------------------------------------------+
| Multi-model  | In MMviB, multi-model constitution refers to          |
| constitution | design-time processes (and activities) of multi-model |
|              | composition (including the workflow design) prior to  |
|              | multi-model experimentation.                          |
|              |                                                       |
|              | This includes, e.g., the selection of plausible       |
|              | single models, the definition of data exchange        |
|              | methods and sequences, the adaptation required        |
|              | thereof, among others, with respect to a given        |
|              | modelling purpose.                                    |
+--------------+-------------------------------------------------------+
| Multi-model  | A multi-model experimental setup describes what is    |
| experimental | required to conduct a multi-model experiment. It      |
| setup        | consists of (1) a multi-model workflow (and workflow  |
|              | parameters), and (2) a multi-model configuration.     |
+--------------+-------------------------------------------------------+
| Multi-model  | In MMviB, multi-model infrastructure refers to all    |
| in           | facilitating services (including software and         |
| frastructure | methods) that enable multi-modelling. The multi-model |
|              | infrastructure does not include the individual        |
|              | independent models themselves.                        |
+--------------+-------------------------------------------------------+
| Multi-model  | A multi-model workflow defines a sequence of tasks    |
| workflow     | (and thereby the sequence of individual model runs    |
|              | and the corresponding dynamic data flow) through      |
|              | which a multi-model experiment can be conducted from  |
|              | initialization to completion.                         |
+--------------+-------------------------------------------------------+
| Multi-model  | In MMviB, a multi-model is an (ensemble) model that   |
|              | consists of two or more single (independent) models   |
|              | that can interoperate to produce meaningful           |
|              | experimental outputs given a predefined modelling     |
|              | purpose.                                              |
+--------------+-------------------------------------------------------+
| Mul          | In MMviB, multi-modelling refers to multi-model       |
| ti-modelling | constitution as well as multi-model experimentation.  |
+--------------+-------------------------------------------------------+
| Operational  | Operational goals have a short-term planning horizon. |
| goals        | They deal with the main question of “how do we plan   |
|              | day-to-day operations”. In terms of scope, these      |
|              | goals are the least broad. The achievement of         |
|              | operational goals leads to the achievement of         |
|              | tactical goals, which leads to the achievement of     |
|              | strategic goals.                                      |
+--------------+-------------------------------------------------------+
| Resolution   | Resolution typically refers to atomic                 |
|              | (non-compositional) granularity, a.k.a. data          |
|              | granularity or data resolution.                       |
+--------------+-------------------------------------------------------+
| Scale        | Scale is the range (or sometimes extent or dimension) |
|              | of the elements or concepts of a model representing a |
|              | source system.                                        |
|              |                                                       |
|              | Scale, in general, implies a mapping relation from a  |
|              | model to its source system. The latter characterizes  |
|              | the range, extent or dimension captured by the model  |
|              | given a modelling purpose.                            |
|              |                                                       |
|              | For example, a wind farm model may simulate the wind  |
|              | energy generation from all wind farms in the          |
|              | Netherlands for the next 10 years. In this case, we   |
|              | say that the geographical (or spatial) scale of the   |
|              | model is the Netherlands, and the time scale of the   |
|              | model is 10 years.                                    |
|              |                                                       |
|              | Scale is often deemed as being temporal or spatial,   |
|              | but it is not limited to these two types. It also can |
|              | be defined with respect to objects, processes, or any |
|              | other subject matters in a source system. For         |
|              | example, a model of a biological system may be at a   |
|              | scale of cell, tissue, organ or beyond.               |
+--------------+-------------------------------------------------------+
| Scenario     | A scenario space consists of a (often large) set of   |
| space        | scenarios that are guided by a modelling goal. An     |
|              | individual scenario goal is informed by a distinct    |
|              | set of (past, current, and/or future) ideals,         |
|              | conditions, and/or constraints, among others.         |
|              |                                                       |
|              | For example, the *II3050* scenario space contains a   |
|              | set of four scenarios that provide a range of         |
|              | projections for future energy prices.                 |
+--------------+-------------------------------------------------------+
| Scenario     | In general, a scenario is the description of one      |
|              | (possible) situation (including actions, events,      |
|              | etc.) that exists or could exist (in the past, at     |
|              | present, or in the future). In modelling and          |
|              | simulation, we refer to a single (configured) model   |
|              | setting as a modelling scenario. Ideally, a           |
|              | simulation scenario (definition) is platform- and     |
|              | model-independent. This means one scenario may be     |
|              | simulated by different models, each of which may have |
|              | a platform- and model-specific setting that is        |
|              | necessary to run the experiments specific to that     |
|              | model.                                                |
|              |                                                       |
|              | For example, the four scenarios in the *II3050*       |
|              | scenario space are the *Europese, Internationale,     |
|              | Nationale, and Regionale sturing (in Dutch)*, each of |
|              | which specifies a projection for future gas and       |
|              | electricity price profiles. An individual scenario    |
|              | goal might therefore be to identify the influence of  |
|              | the different price profiles on energy usage.         |
+--------------+-------------------------------------------------------+
| Scope        | Scope refers to the fact that a modelled set of       |
|              | diverse elements or concepts is a (selected) subset   |
|              | of those in a source system. This modelled set of     |
|              | elements or concepts can represent various aspects,   |
|              | phenomena, ideas, or any subject matters in a source  |
|              | system that deemed relevant given a modelling         |
|              | purpose.                                              |
|              |                                                       |
|              | For example, a wind farm model or a solar farm model  |
|              | can have a scope that includes energy, heat,          |
|              | electricity, economics, finances, and weather         |
|              | conditions. Furthermore, the model may or may not     |
|              | include **the change of** weather conditions. In this |
|              | case, we say that the change of weather conditions is |
|              | within or out of the scope of the model.              |
+--------------+-------------------------------------------------------+
| Simulation   | A (computational) simulation model is a piece of      |
| model        | software that has a set of instructions that defines  |
|              | rules and constraints, among others, for generating   |
|              | input-to-output (I/O) behavior of the model.          |
|              |                                                       |
|              | Simulation is often used to imitate the operation of  |
|              | a real system by executing a model of that system     |
|              | over time. In this case, the model is executed        |
|              | (a.k.a. simulated) iteratively with changing model    |
|              | states by advancing a time axis (a.k.a.               |
|              | time-stepping). Simulation models of this kind are    |
|              | dynamic, as opposed to static models, which do not    |
|              | simulate systems change over time. A (computational)  |
|              | static model is not computed with time-stepping.      |
+--------------+-------------------------------------------------------+
| Source       | A source system is also known as an original system,  |
| system       | a target system, a system referent, a system of       |
|              | interest, etc. It refers to any system that is under  |
|              | modelling interest. This can be, for example, a       |
|              | natural system, an engineered system, a social        |
|              | system, etc., and a combination of any of these       |
|              | systems.                                              |
+--------------+-------------------------------------------------------+
| Static data  | Static data are used to configure the independent     |
|              | variables, sometimes also parameters, in a model.     |
|              | They typically determine the boundary conditions and  |
|              | other initial conditions of a model. For instance,    |
|              | the placement of buildings, cables, and pipelines.    |
|              |                                                       |
|              | Static data are used for model configuration before   |
|              | the start of a simulation run. They are not used for  |
|              | model configuration during a simulation run.          |
+--------------+-------------------------------------------------------+
| Strategic    | Strategic goals have a long-term planning horizon.    |
| goals        | They deal with the main question of “what do we       |
|              | want”. These goals have the broadest scope compared   |
|              | to tactical and operational goals. In terms of        |
|              | cascading effect, strategic plans are cascaded to     |
|              | tactical plans, and subsequently to operational       |
|              | plans.                                                |
+--------------+-------------------------------------------------------+
| Tactical     | Tactical goals have a medium-term planning horizon.   |
| goals        | They deal with the main question of “how do we        |
|              | approach this” where *this* refers to a given         |
|              | strategic goal.                                       |
+--------------+-------------------------------------------------------+
| Uncertainty  | The process of understanding how uncertainty in model |
| analysis     | parameters, model input and model structure affect    |
|              | the model output.                                     |
+--------------+-------------------------------------------------------+
| Workflow     | In MMviB, a workflow task calls a model (run), via a  |
| task         | model adapter, and (if applicable) passes on          |
|              | references to model inputs. An orchestrator calls a   |
|              | workflow task and waits for the model run to be       |
|              | completed and collects a reference to the             |
|              | corresponding model output (i.e., dynamic data).      |
+--------------+-------------------------------------------------------+

Zeigler, B. P., Muzy, A., & Kofman, E. (2018). Theory of modeling and
simulation: discrete event & iterative system computational foundations.
Academic press.

Richard M. Fujimoto (2000), Parallel and distributed simulation systems.
Wiley Series on Parallel and Distributed Computing, John Wiley & Sons.

