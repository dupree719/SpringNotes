# SpringNotes

Spring is all about making things work better together. 

Components:

Controller: 
- Annotated with @Controller (@RestController)
- NO business logic goes here
- Handles incoming requests and building the response
- Request and response stops here and communicates with the business logic
- Coordinate these with service and repository

Service:
- Annotated with @Service
- Contains all business logic 
- Describes verbs/actions of system
- Ensures business object state
- Where transacations should begin 
- Often has same methods of repository but with a different focus

Repository:
- Annotated with @Repository
- Describes nouns/data of the system
- Focused on persisting and interacting with database/crud functions
- One-to-one object mapping
- Often one-to-one database table mapping

Bean: 

JavaBeans are classes that encapsulate many objects into a single object 

A JavaBean is just a standard. A regular Java class that follows certain conventions:

All properties are private (use getters/setters)
A public no-arg constructor
Implements Serializable.


2 Types of Injection:
Setter & Constructor

Setter injection: A matter of calling a setter on a Bean

Key Annotations:
--------------
```
@Service - specifies you intend to use the class as part of your service layer
@Repository - marks a class as part of your data layer, for handling storage, retrieval, and search
@RestController - Component: combines the @Controller and @ResponseBody into a single annotation


@Autowired - Autowiring is the process of placing an instance of one bean into the specified field in an instance of another bean
@Entity - used to mark the persistence objects stores as records in the database

@OneToMany - one-to-many mapping means that one row in a table is mapped to multiple rows in another table. Ex: One cart can have many items.
@ManyToOne - allows for a bidrectional relationship: we are able to access x from y AND also y from x

@Id -  specifies the primary key of an entity
@JoinColumn - helps us specify the column we'll use for joining an entity association or element collection
@Column - used to specify the mapped column for a persistent property or field
@GeneratedValue - provides for the specification of generation strategies for the values of primary keys
@Bean - useful if you have a class that requires an instance of another class as a property
@RequestParam -  allows you to send parameters in the get request and use them in Java
```
