# The Modgen Micro-simulation Technology

Dynamic micro-simulation models can be implemented in three ways: from scratch, using multiple purpose programming languages like C++; using (and extending) statistical packages (e.g., R) with or without combining other tools; and using specialized micro-simulation packages. In this report, we advocate and use the latter approach, specifically, Modgen, a generic micro-simulation technology and language developed at Statistics Canada. Compared with other approaches, using Modgen allows considerable efficiency gains, as it avoids re-inventing the wheel (still a common practice in micro-simulation), allows communication between a large and growing global user group, and, as an industrial-strength product, avoids many programming problems and bugs because many components are ready made and well tested. As a compiled language, Modgen is also very fast, so large-scale models can be implemented with millions of actors that can be run on standard PCs or computer networks.

Modgen (Model generator) is a generic micro-simulation programming language that supports the creation, maintenance, and documentation of dynamic micro-simulation models. Virtually all types of dynamic socioeconomic and sociodemographic micro-simulation models can be accommodated, from small and specialized to large and multi-purpose, in continuous or discrete time, with interacting or non-interacting populations. Furthermore, a model developer does not need advanced programming skills to use Modgen, because Modgen hides underlying mechanisms, e.g., event queuing, and creates a stand-alone model-executable program with a complete visual interface and detailed model documentation. Model developers can therefore concentrate on model-specific code: the declaration of parameters, simulated actors, and events. High-efficiency coding, typically requiring only a couple of lines, can be used to program an output table. Tabulation is done in continuous time and includes a mechanism for estimating the Monte Carlo variation for any cell of any table.

Modgen was designed to facilitate micro-simulation model programming, and its purpose is to remove obstacles to micro-simulation model creation. Obstacles that Modgen eliminates include interface programming, documentation, simulation engine programming, and multi-lingualism. Modgen also provides the interface and simulation engine, and facilitates documentation by automatically creating a hypertext model documentation out of the programming code, and the labels and comments documenting the code. Recent developments include the possibility to publish and run models on the web.

Modgen was developed by micro-simulation modelers and grew by accommodating concrete modeler demands in various application fields covering population projection, health models, and large-scale socio-economic models, e.g., pension analysis. Since it can be shared for free, Modgen is used internally at Statistics Canada and by modelers around the globe, including governments, academia, individual researchers, and international organizations like WHO and OECD (for a list of models using Modgen, consult www.statcan.gc.ca/eng/microsimulation). This wide range of users can also extensively test Modgen in a variety of application fields, contributing to its reliability and stability.

Recent developments in micro-simulation technologies include the development of the open source language OpenM++, a micro-simulation platform inspired by and compatible with Modgen. OpenM++, compared to its free but closed source predecessor, has many distinct features like portability, scalability, and open source. It is currently developed in coordination with Modgen developers, and as an open source project, is expected to reach an even broader user community (http://ompp.sourceforge.net/wiki/index.php/Main_Page). 

In this section, we introduce the Modgen technology from two perspectives: first, the user, then the developer. From the users’ perspective, key features are a clear and easy graphical user interface, high execution speed, full documentation, the ease of modifying and creating scenarios by changing parameters or selecting modeling options, and rich model output in fully labeled tables and micro-data files. From the developers’ perspective, of key importance is the ability to fully focus on the modeling aspects, as most model-independent components are provided and do not require programming.

## The User’s Perspective: User Interface

Modgen models are Windows applications running on standard PCs and share the same graphical user interface, with a menu bar, short-cut icons for key commands, and a help system. The Modgen user interface is organized into two parts: a navigation area displaying a hierarchical list of all parameters, and, after running the model, all output tables. For both parameter and output tables, space is typically devoted to the display area. Parameter tables can be directly edited in the user interface. By changing parameters, users can create and save new scenarios. After running a model, all output tables become available. Table results can be exported into Excel individually or together, to an Excel Workbook.

![](../Figures/image49.jpg)

*Figure: The User Interface*

### Running a model

A typical simulation analysis session will consist of the following actions:

- Opening the model: The user interface opens, both the navigation and the table pane are empty, as no scenario was opened yet.
- Selecting Scenario/Open from the menu or clicking on the open folder icon opens a scenario file. Scenario files have the extension scex.
- The list of available parameters will be visible in the navigation pane. Parameters are organized in tables, which can be accessed by clicking on the table name in the navigation area. For easier navigation, the list of tables is grouped by topic.
- New scenarios can be created by changing parameters and saving the scenario under a new name. The application saves all simulation results with all parameters.
- If the scenario was run before saving, all output tables are available and can be selected like parameter tables.
- Both parameter and output tables can have any number of dimensions. Their complexity can vary from a simple, single on/off check box to multidimensional tables by age, sex, province, year, etc. The user controls which two dimensions of a multi-dimensional table are displayed and which dimensions are selected from a drop-down list. This and other table functionalities are accessible when right-clicking on a table.
- Before running a new scenario, save the existing scenario under a new name, then edit model parameters and settings.
- Users can edit tables directly, including copying and pasting from other tables, such as Excel.
- Besides parameter tables, users can also control a number of scenario settings. These are accessible by selection Scenarios/Settings or clicking the far left icon.
- After setting all parameters and settings as requested, the new scenario can be run by selecting Scenario/ Run or clicking the RUN icon.
- The updated list of model results tables is then available.

![](../Figures/image50a.jpg) 
![](../Figures/image50b.jpg) 
![](../Figures/image50c.jpg)

*Figures: Scenario Settings*

### Scenario Settings

Important settings are:

- General tab:
    - The time horizon of the simulation.
    - The number of replicates produced: if the model is run more than once, distributional information is automatically generated from the individual model runs and results tables automatically average all results.
    - Number of threads: various replicates can be run in parallel, depending on the number of available processors.
    - Starting seed (of random numbers): when rerunning a model with the same seed, it will produce identical results.
    - Copy parameters to the output database: useful when exporting simulation results to Excel workbooks, which then can include all parameters of the model, too.
- Parameter Files tab: can see, change, or add parameter files belonging to the scenario. When saving an existing scenario under a new name, all parameter files of the model will automatically be copied with a file name consisting of the scenario name and data file name. Usually no user operations are required.
- Tables Tab: displays the list of available output tables. Tables can be de-selected if not needed.
- Documentation tab: users can place and store scenario notes here.

### Model Results

Model results come in three forms:

- A list of tables displayed directly within the application. Besides the table values, tables can contain additional views (e.g., of distributional information of table cells) and functionalities. With multi-dimensional tables, users control the order in which to display table dimensions and details like the number of decimal places. Tables can also contain documentation. Tables are labeled, adding to the readability of the output.
- Micro-data files to be further analyzed using statistical software (depending on the model). The population projection model for examples can produce periodic files (the user sets the first time point of file output and the time interval for repeated output) of a list of variables, which the user selects. Output is written into CSV text files, which have a header row with variable names.
- A sample of individual life-course data, which can be displayed graphically using the BioBrowser application. This feature is not used in the population projection model, but is very useful, especially for debugging, as it can filter “strange” cases and study simulated lives in full detail.

![](../Figures/image51.jpg)

*Figure: BioBrowser*

### Output Table Views

Right-click tables and select Properties to access additional information and change the table’s display.

![](../Figures/image52a.jpg)
![](../Figures/image52b.jpg)
![](../Figures/image52c.jpg)

*Figures: Table Properties*

- Info tab: contains information on the internal table name, its label, and, if available, a note
- Dimensions tab: allows users to change the order of dimension in which a table is displayed
- Decimals: allows users to change the number of decimal spaces
- Transformation: selects alternative types of values for display. The default is Value, which is the simulation results. If several replicates are run, results of individual runs can be displayed,or, most importantly, distributional information accessed

### Exporting Simulation Results

There are three ways to export table results for further use and analysis (e.g., in Excel):

- The content of individual tables or table cells can be directly copied and pasted, either by marking cells or by right-clicking on a table and selecting copy from the Context menu. In this case, table values are copied without row, column, or table labels.
- Right-clicking on the table also enables the Copy Special option. Here, the current table view or all dimensions of the table together can be copied, including all dimension and table labels.
- The Scenario/Export menu lets users choose tables to be exported together into an Excel Workbook. Dialog selects the display format for tables (including pivot table format) and chooses a file name.

### Further documentation

The user interface is fully documented within the application. Users can use the help menu to access a detailed hyperlinked help option, which covers all capabilities relevant to model users, such as editing parameters, creating scenarios, running the model, and viewing and exporting model results.

![](../Figures/image53.jpg)

*Figure: The Help System Documenting the User Interface*

Similar to the model’s user interface, the model itself is fully documented within the application. Users can access encyclopedic documentation from the help menu, including descriptions of the modules, parameters, model actors, and all table output.

![](../Figures/image54.jpg)

*Figure: The Model Documentation System*



## The Developer’s Perspective: Key Programming Concepts

This chapter gives some flavor on Modgen programming. A detailed step-by-step guide to implement the DYNAMIS-POP model is given in teh following chapters. A detailed technical developer’s guide is also available for the Modgen language; it is integrated in the Modgen’s help option and available as a pdf at [http://www.statcan.gc.ca/microsimulation](http://www.statcan.gc.ca/microsimulation).

Modgen requires and integrates into the Microsoft Visual Studio C++ package, thus making use of one of the most popular programming interfaces and its powerful debugging tools. Modgen translates Modgen code into C++ code, which is then compiled into a C++ application, combining the strengths of the generic C++ language with specialized micro-simulation language concepts and functions. A model developer does not need to have advanced programming skills to use Modgen, because Modgen hides underlying mechanisms like event queuing and automatically creates a stand-alone model-executable program with a complete visual interface and detailed documentation. Developers can therefore concentrate on model-specific code: the declaration of parameters, simulated actors, states, events, and table output.

### Parameter Dimensions and Tables

All parameters in Modgen are organized in tables, which can be as simple as a single on/off checkbox or a multidimensional table. Data types can be logical, integer, or real numbers. To define parameter dimensions, Modgen has three key concepts: classifications (for categorical variables), partitions (to split a continuous variable or time into pieces), and ranges (a set of integer values). Parameters are declared in a parameters {}; block.

````
classification  SEX                                         //EN Sex
{
    FEMALE,                                                 //EN Female
    MALE                                                    //EN Male
};
partition       AGE15       { 15, 30, 45, 60, 75 };         //EN 15 year age groups
range           PROJ_YEARS  { 2015, 2060 };                 //EN Projected years range

parameters
{
    double      EmigrationRate[SEX][AGE15][PROJ_YEARS];    //EN Emigration Rate
};
````

Note that the code comments, which is the text introduced with //EN (where “EN” is defined as English language; Modgen supports multi-lingual models), are used to automatically label the resulting tables in the user interface. Use the code above to create a parameter table to display on the user interface and make accessible in the program.

![](../Figures/image55.jpg)
*Figure: The Parameter Coded Above*

The parameter values are stored in .dat text files, usually in groups or all parameters together in one or several file(s). The syntax is identical to the programming code, except that values are provided:

````
double      EmigrationRate[SEX][AGE15][PROJ_YEARS] = { value1, value2,...};
````

### Actors, states, functions and event declarations

Actor is an entity whose life is simulated in a Modgen model. There can be different types of actors in a model, and Persons is typically the most important. Actors are characterized by state variables as well as the functions and events that change the states. Some states can be numerical (e.g., age, income) and others are categorical (e.g., gender, marital status). In Modgen, simulation takes place through the execution of events. Each event consists of two functions: a time function to determine the time of the next occurrence of the event, and an implementation function to determine the consequences when the event happens.

Modgen supports three types of state variables:

- “Simple” states those that are updated in events
- “Derived” states those that depend on other states and update themselves, e.g., a formula in an Excel table cell
- “Self-scheduling” states those that update themselves following a pre-specified time schedule

Two state variables, time and age, are supplied and maintained automatically. States and events belong to a specific actor and are declared in an actor block:

````
actor Person
{
    SEX         sex = { FEMALE };                           //EN Sex
    logical     resident = { TRUE };                        //EN Resident

    int         age_years = self_scheduling_int(age);       //EN Age in full years
    int         age_index = split(age_years, AGE15);        //EN Age group index
    int         simulated_year = self_scheduling_int(time); //EN Calendar year


    event       timeEmigrationEvent, EmigrationEvent;       //EN Emigration Event
};
````

In the previous example, we define:

- Sex and resident as simple states, initialized with a value in {} brackets
- Age_years as a self-scheduling state, creating its own schedule to be updated exactly at the right moment independent of other events in the model
- Age_index is a derived state, when age_years changes, it is updated when a new age group limit is achieved
- An event “EmigrationEvent”

### Event Implementation

Each event consists of two functions, one returning the time of an event, the second accessed if the event happens. Typically, the time of an event is based on piece-wise constant hazard models, with the waiting time assumed to be exponentially distributed for a given hazard rate, which is assumed to be stable over specific pieces or episodes of time. For example, it is assumed that the emigration hazards will stay constant for a given age range and calendar year. When the age group or calendar year changes, Modgen automatically generates a new waiting time based on the new applicable rate. For a given hazard rate, a random waiting time can be calculated as -ln(RandUniform)/hazard.

````
TIME Person::timeEmigrationEvent()
{
    double dHazard = EmigrationRate[sex][age_index][RANGE_POS(PROJ_YEARS, calendar_year)];

    if ( resident && WITHIN(PROJ_YEARS, calendar_year) && dHazard > 0.0)
    {
        return WAIT(-log(RandUniform(29)) / dHazard );
    }
    else return TIME_INFINITE;
}

void Person::EmigrationEvent()
{
    resident = FALSE;
}
````

For persons at risk of emigration (i.e., residents within the simulated timeframe and positive hazard rate), a random waiting time to emigration is calculated based on the given rates. Note that Modgen automatically handles an event queue and automatically updates waiting times whenever a state affecting the waiting time changes. The second function, EmigrationEvent(), implements emigration itself: the event sets the simple state “resident” to FALSE.

### Table output

Modgen contains a powerful tabling language, and even complex tables usually require only a few lines of code. Tables belong to an actor and consist of a name, a label, and one or more table expressions, e.g., formulas for the calculation of output values. Tables can be divided by an unlimited number of dimensions (e.g., output by age and sex) and can contain a filter which selects who should be included in the table and/or when the table should be created.

For example, the following table calculates the simulated emigration hazards by age group, sex, and calendar year. For sufficiently large simulated populations, the simulated rates should come close to the parameter.

The table filter (second line, within [] brackets) selects the timespan for which the table is produced. The table dimensions are projected calendar years, age group, and sex, as in the parameter table that drives the model. Age groups can be built automatically in the table for a given partition using split(). The sign after a table dimension indicates that the table should also calculate totals over all categories of a variable.

````
table Person SimulatedEmigrationRates                               //EN Simulated Emigration Rates
[ WITHIN(PROJ_YEARS, calendar_year)]
{
    sex+ *
    {
        transitions(resident, TRUE,FALSE) / duration(resident,TRUE) //EN Emigration Rate decimals=4
    }
    * split(age_years, AGE15)                                       //EN Age group
    * proj_years
};
````

Modgen has a long list of functions used in tables. The functions used here are transitions(), which count the number of specific transitions specified, and duration(), which calculate the time spent in a certain state. With these functions, rates can easily be calculated as the number of events divided by the time at risk.

![](../Figures/image56.jpg)
*Figure: An Output Table Displaying Simulated Rates*

### Model documentation

Modgen automatically produces a hyperlinked help file containing model documentation based on the model code as well as labels and notes within the code. Variable labels and other information within the code are also used for producing a fully labeled user interface, including labeled output tables (e.g., table name, variable names, and description of variable dimensions).

### Programming Wizards and Model Templates

In addition to the ample functionality provided automatically, with the underlying code hidden from the developer, Modgen also provides code wizards to generate the essential code of new models, add micro-data input modules, and create new “empty” modules. Code produced by the wizards is visible, but usually does not require any changes by developers, or just minor adaptations, like the specification of variable names in the case of micro-data input files.

Alternatively, developers can start from existing models. The step-by-step creation of the population projection model supports this approach, as the first steps are very generic and modelers can depart from such earlier steps when building models. 