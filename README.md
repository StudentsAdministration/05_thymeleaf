# #5 Thymeleaf
Thymeleaf examples and literature used this semester

## Pourpouse of Thymeleaf
Thymeleaf is a scripting language which your are going to use primary for handeling the data transfered from the controller or the data transfered from the view to the controler. 


## Adding external stylesheet

````html    
      <link rel="stylesheet" type="text/css"
          href="../../static/css/styles.css"
          th:href="@{css/styles.css}"/>
````   
This assumes that you will put the styles sheet (e.g styels.css) file in the folder:  **resources -> css**


## Variables
   



* [Standard URL Syntax](http://www.thymeleaf.org/doc/articles/standardurlsyntax.html)


## loop
When you get a list (e.g Arraylist) you need to "loop it" in order to get a specific entity. A loop  look like this
````html
      th:each="student: ${stu}"
````    
This you can add to a html tag like this

````html
      <tr> th:each="student: ${stu}">
            <td th:text="${student.getFirstName()}">
      </tr>
````   
