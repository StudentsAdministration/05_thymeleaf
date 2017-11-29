# #5 Thymeleaf
Thymeleaf examples and literature used this semester

## Pourpouse of Thymeleaf
Thymeleaf is a Java Template Framework which your are going to use primarely for handeling the data transfered from the controller or the data transfered from the view to the controler. 


## Adding external stylesheet

````html    
      <link rel="stylesheet" type="text/css"
          href="../../static/css/styles.css"
          th:href="@{css/styles.css}"/>
````   
This assumes that you will put the styles sheet (e.g styels.css) file in the folder:  **resources -> static -> css**


## Variables
   



* [Standard URL Syntax](http://www.thymeleaf.org/doc/articles/standardurlsyntax.html)


## loop
When you get a list (e.g Arraylist) you need to "loop it" in order to get a specific entity. A loop  look like this
````html
      th:each="student: ${stu}"
````    
This you can add to a html tag like this

````html
      <tr th:each="student: ${stu}">
            <td th:text="${student.getFirstName()}">
      </tr>
````   
## Thymeleaf Layout
You can "compose" a page of several elements. A main html page that includes a menu etc.

[Thymeleaf Standard Layout System](http://www.thymeleaf.org/doc/articles/layouts.html)

````html    
      <div th:replace="fragments/header :: header" />
      <!-- ============================================================================ -->
      <!-- This content is only used for static prototyping purposes (natural templates)-->
      <!-- and is therefore entirely optional, as this markup fragment will be included -->
      <!-- from "fragments/header.html" at runtime.                                     -->
      <!-- ============================================================================ -->
````    
