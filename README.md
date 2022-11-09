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
Constructor: Where object's constructor is used to inject dependencies

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

API Book Notes:

To make a valid request, the client needs to include four things:
 1 URL (Uniform Resource Locator) 
  In HTTP, a URL is a unique address for a thing (a noun). 
  
 2 Method
 The request method tells the server what kind of action the client wants
the server to take.

 3 List of Headers
 Headers provide meta-information about a request. They are a simple
list of items like the time the client sent the request and the size of the
request body. 

 4 Body
 The request body contains the data the client wants to send the server. 
 
 
 HTTP Responses: 
 HTTP responses have a very similar structure to requests. The main difference is that instead of a method and a URL,
 the response includes a status code. The response headers and body follow the same format as requests.
 
JSON:
JSON is a very simple format that has two pieces: keys and
values. Keys represent an attribute about the object being described. A
pizza order can be an object. It has attributes (keys), such as crust type,
toppings, and order status. These attributes have corresponding values
(thick crust, pepperoni, and out-for-delivery).

XML:
XML has been around since 1996. Like JSON, XML provides a few
simple building blocks that API makers use to structure their data.The
main block is called a node. 

OAuth: an authentication scheme that automates the key
exchange between client and server.

Access Token: a secret that the client obtains upon successfully
completing the OAuth process.

Scope: permissions that determine what access the client has to
user's data. 

SOAP: API architecture known for standardized message formats

REST: API architecture that centers around manipulating
resources

Resource: API term for a business noun like customer or order

Endpoint: A URL that makes up part of an API. In REST, each
resource gets its own endpoints

Query String: A portion of the URL that is used to pass data to the
server

Query Parameters: A key-value pair found in the query string
(topping=cheese)

Pagination: Process of splitting up results into manageable
chunks
