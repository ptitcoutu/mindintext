# Data, Databases, Middleware and Caches
When you build a software to improve or bring new solutions to "humans" we have to understand data.

## Data nature
I retains two way to explain data natures:
* ability to manage easily data by computers
* source and meaning of the data for human and computers

### Non digital data vs Digital data

### Source and Meaning of data
There are three kinds of data source:
* data provided as input or captured as output of an operation
* knowledge or what we call "facts"
* data deduced from captured data and or knowledge

In software development sometimes we distinguish commands and events to talk about input and output of operations and state to talk about a snapshot of collected event data at a given time (see CQRS architecture).
But in human activities we've got another element to consider which is contextual data and the fact that the data come from outside or inside this context.

## Data storage
### Paper and brain storage
### In memory storage
### Simple file storage
### Document Storage and bigdata storage
### Relational Storage
### Graph Storage
### Olap Storage
## Data processing
### Correlations and Aggregation
### Simple analysis
### Simulation and prediction
## Data Migration
### Oneshoot vs Incremental Data Migration
Most of the time when you change your application to add new feature or change an existing one 
you have also to change data structure stored in the database.
You can use several solution to migrate data:
* stop your application, launch some queries to apply the change and then, deploy the new version of the application with the new structure
* have both the previous structure and the new one at the time and have a translation at the application level in order to be able to manage both versions at the same time in order to do a smooth migration without service interruption 
The first approach is easier because you have only one version of the structure and application at the same time.
The second approach is harder to manage but you can manage the increased complexity using abstraction layer.
You can also do more little increment using the second approach because you have the ability to migrate just a part of your code to deploy more quickly and have a first feedback on the change.

Some tools like liquibase are essentially used for the first approach. This way you have several scripts and thoses scripts are recorded to be played just once in the correct order each you start your service.
I didn't find a tool to ensure the second approach. 

If you want to have both structure versions at the same time you have to save this version in the related data.
This could be harder to achieve in case of classical relational database.
