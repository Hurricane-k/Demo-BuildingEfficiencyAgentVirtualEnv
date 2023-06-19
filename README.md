# What is it for

This is a simple example of how to train agent for building energy efficiency in virtual environment without the help of other external software, like [fmi](https://fmi-standard.org/) or [OpenModelica](https://openmodelica.org/). If you are interested in how research crowd do similar things, I write a [blog](https://carrybio.netlify.app/posts/blog12/) to summarize it briefly.

# What does it have

In my example, to make it comprehensive, model-based and model-free are in this example. Model-free is to do load allocation by Q-learning. Model-based is to control the number of cooling towers and frequency of fans in them.  

For every load, model-free is followed by model-based (load allocation first and then cooling tower control). 

In model-free method, reward is about total COP ($COP_{total}=\frac{load}{P_{chillers}+P_{pumps}+P_{towers}}$). that will be independent of any RL relevant package. In model-based method, goal the minimum of total energy consumption.

# Configuration

The virtual system is a classical water system (chillers + water pumps + cooling towers).

| Category | Details                                                                                                                                                                                                                                                                                                                                                                              |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Chillers | Chiller#1: with larger capacity, two chillers in total<br/>Chiller#2: with smaller capacity, one chiller. (details in .ipynb 7. subfunction)                                                                                                                                                                                                                                         |
| Pumps    | Chilled Water Pump#1: with more nominal waterflow in nameplate Fixed Freq, two pumps in total<br/>Chilled Water Pump#2: with less nominal waterflow in nameplate Fixed Freq, one pump<br/>Cooling Water Pump#1: with more nominal waterflow in nameplate Fixed Freq, two pumps in total<br/>Cooling Water Pump#2: with less nominal waterflow in nameplate Fixed Freq, one pump<br/> |
| Tower    | All Cooling Towers are idential, with variable-speed fans                                                                                                                                                                                                                                                                                                                            |

![drawing.jpg](https://github.com/Hurricane-k/BuildingEfficiencyAgent_in_VirtualEnv/blob/main/SystemLayoutAbstract.jpg)



# Hard Things to Solve






