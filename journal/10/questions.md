# CSharp and SQL Fundamentals
01. What is the purpose of a `namespace`?

  > | This declares a scope of related objects for the page. It helps with organizing elements and functions and creating globally unique types. They help with internally organizing within the page to keep functions and elements together, but also for external organization system to present elements to other portions of the code. |

02. What is the difference between a `class` and an `interface`?

  > | A class has a defintion and an implementation. Interfaces only have definitions. Interfaces contains behaviors that the class contains and defines, while the class describes how an object behaves. |

03. What is the method that returns an instance of a class, yet it has no return type?

  > | Void. Null can be used to show the absence of something that should be there, while void just says "there is nothing here" and leaves it at that. |

05. In the Car example what is the access modifier of the `Start()` method?

  ```c#
  abstract class Car
  {
    public string Start()
    {

      return "Vroooom";

    }
  }
  ```

  > | Public. This allows anyone to set and get within the function of Start. |

06. In the Car example what is `string` an indication of?

  > | String explains how Start returns it's functionality. In order for "Vrooom" to come back as a string, the function needs to have the 'string' type listed prior to it.  |

07. In the Car example what is `abstract` preventing?

  > | Instantiation. Abstract classes can't be instantiated. This allows multiple classes or abstract methods to use it |

08. In a SQL table, what is the difference between information in a row and information in a column?

  > | Columns hold all the same information for the same field. like column "name" contains all the names within the table for multiple inputs. Rows contain all the information within one group. like all the ingredients or information about a single album. |

09. Demonstrate the necessary SQL for creating a table called `characters` with the values `name, age, description` as strings, and an `int` id.

  > | CREATE TABLE characters(
     id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        age VARCHAR(750) NOT NULL,
        description VARCHAR(255) NOT NULL,
  ) |

10. In SQL how can you query more than a single table? Provide an example.

  > | by using 'select' and 'join'. 
     string sql = @"
    SELECT
    alb.*,
    creator.*
    FROM albums alb
    JOIN accounts creator ON alb.creatorId = creator.id;
    "; |
