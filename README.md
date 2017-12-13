# #5 Thymeleaf
Thymeleaf examples and literature used this semester

## Pourpouse of Thymeleaf
Thymeleaf is a Java Template Framework which your are going to use primarely for handeling the data transfered from the controller or the data transfered from the view to the controler. 

## The th: tag
Thymeleaf works by adding an attribute to the html tags in your document. From the teachings about HTML and Css you know that html tags can have [attributes](https://www.w3schools.com/html/html_attributes.asp). 

Thymeleaf tags all follow the pattern: 

````        
      th:text="${nameOfVariable}"
````     
An example of that is

````    
      <tr>
            <td th:text="${student.name}"></td>
      </tr>
````         
or  
````      
      <input type="text" th:field="${student.name}" />
````     
## Adding external stylesheet

````html    
      <link rel="stylesheet" type="text/css" th:href="@{css/styles.css}"/>
````   
This assumes that you will put the styles sheet (e.g styels.css) file in the folder:  **resources -> static -> css**


## Variables
A variable from the Model (added by ````model.addAttribute("student", new Student())```` in the controller) can be accessed like this 

````    
     ${object.method()} 
````    

````    
      <p th:text="${student.name}" />
````    
We can and will also use another way of accessing the object and its members. When using a HTML form we can like this:

````    
     <form th:action="@{/create}" method="post" th:object="${student}">
            <input type="text" th:field="*{name}" />
            <input type="submit" value="Create" />
     </form>
````    
So the \*{name} access the name variable of the ${student} object.    
The @ in  ````th:action="@{/create}"```` is used for pointing out links or urls.

### Links with an id
Wy will need the functionality of sending a variable via the url like:

````    
      http://localhost:8080/update?id=3
````   
For this we will use the folowing syntax    

````    
      th:href="@{/update(id=${student.studentId})}"
````    
The documentation can be found here:    
* [Standard URL Syntax](http://www.thymeleaf.org/doc/articles/standardurlsyntax.html)    

## loop
When you get a list (e.g Arraylist) you need to "loop it" in order to get a specific entity. A loop looks like this
````html
      th:each="student: ${stu}"
````    
This you can add to a html tag like this

````html
      <tr th:each="student: ${stu}">
            <td th:text="${student.getFirstName()}">
      </tr>
````    



_<div align="right">&copy; clbo@kea.dk</div>_
