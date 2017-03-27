## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
```
AR is a ruby library used to interact with relational databases like SQL using a bunch of built-in methods.
```

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

```
Team.find_or_create_by()
Team.find_by()
Team.create
Team.new & Team.save
Team.destroy
Team.update

They are built-in ActiveRecord methods.
```

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
```
Team.find(4)
Team.find(4).owner_id
```

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
```
Team.find(4).owner
```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.
```
The relationship will be a many-to-many; students have many teachers, and teachers have many students. Therefore we'll need a join table that holds the foreign keys of the primary keys of both the teachers table and students table. Like so: 

students
id | name | cohort

teacher
id | name | homeroom

student_teacher_relationship (join table)
id | teacher_id | student_id

```
6. Define foreign key, primary key, and schema.
```
The foreign key is a primary key of a table that lives inside another table to signify a relationship. The primary key is the core id of a particular table. A schema is the framework for the database (i.e. the structure of relationships and tables and their columns and names of each column and primary keys and foreign keys they might hold for other tables).
```
7. Describe the relationship between a foreign key on one table and a primary key on another table.
```
A foreign key on one table IS the primary key of another table in a defined relationship. In other words, in a one-to-many relationship, the "many" table holds a foreign key that links to the primary key of the "one" to link the relationship.
```
8. What are the parts of an HTTP response?
```
status, headers, body
```
### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
```
.find_or_create_by() - finds or creates (if it doesn't exist) that which you pass in as an argument
.pluck() - "plucks" out the corresponding data matching the argument you pass in (column name) and returns a list of the plucked items (all items in that column)
.where() - finds all instances of what you're looking for and returns in a list
.create - creates and saves a new record to the database
.minimum() -returns the smallest item in the column, or .maxium() -returns largest item in the column
```
2. Name your three favorite ActiveRecord rake tasks and describe what they do.
```
rake db:reset (drops, creates, and seeds)
rake db:migrate (runs migrations that haven't yet run)
rake db:test:prepare and then rake db:environment:set when the test:prepare throws an error (i'm not totally sure, but this combo saved us a lot in bike share...)
```
3. What two columns does `t.timestamps null: false` create in our database?
```
created_at
updated_at
```
4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
```
One-to-many relationship; teachers have one school and a school has many teachers. Teachers table will hold a foreign key to the schools table that matches its primary key.
```
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
```
teachers
id | homeroom | subject_taught | school_id

schools
id | city | principal_name
```
6. Give an example of when you might want to store information besides ids on a join table.
```
??? I will google this, but may warrant class discussion (unless you mean besides the join table's primary key (id), then you'd want to store the primary keys of the two tables the join table is connect as foreign keys in the join table).
```
7. Describe and diagram the relationship between patients and doctors.
8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?
```
repetive information like the same form format for more than one thing
```
