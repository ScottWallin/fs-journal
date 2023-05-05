# Intro to JavaScript
01. Which keywords are used to declare a variable in JavaScript?

    > | Let, Var, & Const |

02. What is the definition of a function?

    > | Functions are statements that that perform a task or calculate a value. |

03. What are the `SOLID` principles?

    > | Single responsibility principle, Open/closed principle, Liskov substituion principle, Interface segregation principle, Dependency inversion principle.  |

04. Given this array: How could you remove the `pineapple`?

    ```js
    let fruit = ['apple', 'banana', 'pineapple', 'orange', 'strawberry']
    ```

    > | you could do 'delete fruit[2], but that would still leave position 2 open in the array. To remove it, but then change the array to contain four items with no holes, I'm not too sure. |

05. Given these two objects: How could you add each to the others friends arrays?

    ```js
    let you = {
        name: "You",
        hair: true,
        friends: []
    }
    let them = {
        name: "Them",
        hair: false,
        friends: []
    }
    ```

    > | I'm a little confused on this one. I don't remember going over this in lectures, so I looked through the readings and on w3. Best I could find, using the join() method would work to add these two objects. I believe it would be let you.friends = them.join("Them") |

06. Give an example of a JavaScript `Conditional`:

    > | if (pen > sword){
        console.log ('huzzah')
    } |

07. What is the main difference between `parameters` and `arguments`?

    > | My weak point. Arguments allow the draw function to be used, while parameters name the function. |

08. Instead of writing everything to the console, what is a better way to debug your code?

    > | use the debugger tag so you can run through each line of code individually.r |

09. What is the difference between a `primitive` value and a `reference` value?

    > | a primitive value holds it's information within itself. like a number or boolean, its value is exactly what it says. reference values place their value in what they reference. they're like a key to access larger pieces of information held in arrays or objects. |

10. Demonstrate a loop that prints the numbers between -100 and 100?

    > | I know I know this one, I accidentally set an infinite loop twice on my computer and crashed it both times doing balloon pop. My brain hurts. 
    for (i = -100; i <= 100; i++)
        console.log(i)|
