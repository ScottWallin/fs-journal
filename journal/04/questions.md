# Understanding Asynchronous Code, and API's
01. What is the difference between `asynchronous` code and `synchronous` code?

  > | Async constantly happens and doesn't wait for another function to happen before it can do whatever function is required of it. synchronous goes in a specific order. the following function can't be done until the first one is finished.  |

02. What is an event listener?

  > | X.on. It listens to the functions going on or changes in state, and doesn't activate until the specific function or change it's listening for is invoked. it helps with timing of functions or getting specific functions to activate when something is added or a state is changed. |

03. What does *REST* stand for, and in simple terms what does it mean??

  > | it stands for representational state transfer. it allows for easier communication between our systems we have as a consumer, and the servers and databases of the applications we're accessing. It doesn't matter what device or program we're using to access, as long as the permissions are there.   |

04. What is a callback / higher order function?

  > | callbacks are functions that are passed into other functions. this allows for better control of when a function will be invoked. when you have one funciton, you'll place the next within it. so when the first function is called, the next is called after. |

05. What is a `promise`? How do you capture an error from a `promise`?

  > | It's like a placeholder from the invocation of an asynchronous function. it holds the promise of providing the value of whether the function worked or failed. to catch the error you need a try catch pop. try to attempt the function, catch for the result, then pop to show the error if it occurs.  |

06. Name three processes used to make requests over `HTTP`?

  > | post to send your inputs to the array or page. get to retrieve data from the server. put to retrieve data but the exact same data each time.  |

07. What does the `API` acronym stand for?

  > | Application Programming Interface.|

08. What must you do in order to `await` a promise inside of a function?

  > | In order to use await, you need to have 'async' before the function. the values will then be returned when the promise is fulfilled. |

09. What is the purpose of encapsulation in programming?

  > | This brings everything together into one cohesive unit. Makes it easier to separate the information that you don't want the user to see from the information they can see and the controlling functions used to manipulate the dom.  |

10. What is `HTTP` response code for a successful request?

  > | 200 |

11. What is a 400 error?

  > | Means a bad request being sent to the URL. Something needs to be changed at that point or is missing. Or the path is missing and the name put in the model doesn't match and needs to be fixed.  |
