OPERA
=====

OPERA is an optimization model based on linear programming. It represents the entire energy system of the Netherlands,
including bunker fuels, feedstocks and all domestic greenhouse gas (GHG)emissions. It is possible to optimize for
individual years, but also to optimize over a period of years (a dynamic optimization). The user can define several
policy relevant targets, like a GHG reduction target, a final energy consumption target, etc. Furthermore individual
technologies, groups of technologies and resources can be restricted by maxima or minima. For example a maximum capacity
potential for wind offshore can be set. The model will decide if this maximum is needed.

OPERA makes use of time-slices, in which hours with a similar character are grouped in the same time-slice. Input data
with an hourly resolution are aggregated in these time-slices. Example of hourly input data are hourly wind speeds and
the hourly electricity demand profile for the household sector. The time-slice settings can also be set such that an
n-hourly resolution is achieved.

The driver of the model is the demand for energy. The most significant amount of demand is determined via service
demands.  Examples are a predefined amount of tons of steel that need to be produced, passenger kilometers that need
to be driven by cars, etc. In all these cases the model determines what technologies are used to fulfill these service
demands. And therefore the final demand for energy carriers is also not predefined in advance. For a remaining part of
the energy system, which is too small to represent in individual types of service demand, a remaining final electricity
and heat demand per sector needs to be fulfilled.

The user has the possibility to subdivide the Netherlands in regions. These regions can be connected with each other
via transmission infrastructure. Import and export of electricity with neighboring countries is not determined
endogenously, but is covered by coupling the model to an European electricity market model.

For more information, see `Netbeheer Nederland datasheet about OPERA <https://www.netbeheernederland.nl/_upload/Files/Rekenmodellen_21_2b9d3fa8e4.pdf>`_