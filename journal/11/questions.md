# A bit more CSharp and SQL
1. What does ***inheritance*** accomplish for us in C#?

  > | Similar to extends in Node. It's used by putting a : between the class and the class that's being inherited. It allows us to pull all the information from the inherited class and reuse it within another class. |

2. How does ***member inheritance*** work in C#? Does a `Class` inherit all members of the base `Class`?

  > | It allows us to define a child class that modifies, inherits, or extends a parent class. It only inherits the members that are listed as public. Anything listed as private won't be inherited.  |

3. How does ***accessibility*** affect inheritance?

  > | This determines how something can be inherited or viewed. When they're inherited, the access could change within the new class after they've been inherited.  |

4. What is the difference between a `PRIMARY KEY` and a `FOREIGN KEY`

  > | The primary key defines a specific row from the table the primary key is on. The foreign key defines a separate table that has information being pulled in and referenced to the new table. Primary keys also can't take anything NULL, while foreign keys can.|

5. What is an ***alias***?

  > | Aliases give tables, rows, or columns a temporary name. They only work within the duration of the query. |

6. Demonstrate how you would query a join statement that would get all of a doctors patients from the following collections:

  ```SQL
  CREATE TABLE doctors (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patients (
    id INT NOT NULL AUTO_INCREMENT,
    -- CODE OMITTED
    PRIMARY KEY (id)
  )

  CREATE TABLE patient_doctors (
    id INT NOT NULL AUTO_INCREMENT,
    doctorId INT NOT NULL,
    patientId INT NOT NULL,

    FOREIGN KEY (doctorId)
      REFERENCES doctors(id),
    FOREIGN KEY (patientId)
      REFERENCES patients(id),
  )

  ```

  > | SELECT * FROM patients pat
      JOIN patient_doctors
      WHERE pa |
