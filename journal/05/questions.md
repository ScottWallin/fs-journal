a# Intro to Server side concerns with JavaScript
01. What do the letters of the acronym `CRUD` stand for?

  > | CRUD stands for Create, Read, Update, & Delete.  |

02. Each action that `CRUD` represents maps to an HTTP request. What HTTP request does each `CRUD` action correspond to?

  > | Create goes with Post. Read goes with Get. Update goes with Put. Delete is simple and goes with delete.  |

03. What does `ORM` stand for? Which `ORM` do we use when interacting with MongoDB

  > | Object-Relational Mapping. With MongoDB, ORM enforces using a schema within your model, manages working data to objects, and it helps strengthen the connection and interactions by removing the need to write database query language.  |

04. Which two `HTTP` request types include a body?

  > | Post requests and put requests include a body|

05. In a/an _______ coding model, when you call a function, it returns only when the action has finished and stops your program for the time the action takes. Likewise in a/an _______ coding model, multiple things are allowed to happen at one time. When you perform an action, your program continues to run.  Fill in the blanks.

  > | the first blank describes a synchronous coding model. the second one describes an asynchronous.  |

06. What are the three types of data relationships? Provide an example of each.

  > | 1:1, 1:Many, & Many:Many. 1:1 relationships where each only pertains to the other. Like an author to an address. One author lives at one address. One address belongs to one Author. 1:Many is one thing containing many, but each of those many things only go with the one thing. like a book and pages. One book has many pages, but each page only goes to the one book. Many:Many is like a singer and a song. Many singers can sing the song. While a song might have multiple singers.   |

07. What is middleware?

  > | Request, Response, Next. They go in the () of a function that's to be invoked and goes with the try/catch/next within the function as well. Request tells the server we're looking for information. respond tells the server we're receiving data with this function. |

08. The ______ pipeline delivers information from the client while the ______ pipeline returns it. Fill in the blanks. 

  > | the request pipeline delivers information from the client, while the response pipeline returns it.  |

09. Demonstrate the pattern that is used to include a request query with the client's `HTTP` request providing the property `tag` and the value `winter`.

  > | const winter = req. mmmm actually i have no clue |

10. What is a ***virtual property***?

  > | It's a property that isn't stored in the database. They're usually used for computing properties.  |
