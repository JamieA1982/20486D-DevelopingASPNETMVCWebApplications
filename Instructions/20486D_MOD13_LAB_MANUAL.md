# Module 13: Implementing Web APIs

# Lab: Implementing Web APIs

#### Scenario



#### Objectives

After completing this lab, you will be able to:


#### Lab Setup

Estimated Time: **60 minutes**

### Preparation Steps

1.	Ensure that you have cloned the **20486D** directory from GitHub. It contains the code segments for this course's labs and demos. (**https://github.com/MicrosoftLearning/20486D-DevelopingASPNETMVCWebApplications/tree/master/Allfiles**)

### Exercise 1: Adding Actions and Call them using Microsoft Edge

#### Scenario

You are required to...

The main tasks for this exercise are as follows:

1.	Add an action to a Web API application

2.	Run the application

3.	Add an action that gets a parameter to a Web API application

4.	Run the application

5.	Add a Post action to a Web API application


#### Task 1: Add an action to a Web API application

1. Create a new folder with the following information:

   - Project: **Server**
   - Folder name: **Controllers**
   
2. Create a new controller with the following information:
   - Controller name: **RestaurantBranchesController**
   - Template: **API Controller - Empty**
   - Folder: **Controllers**
   
3. In the **RestaurantBranchesController** class, add **using** statements for the following namespaces:
   - **Server.Data**
   - **Server.Models**

4. Create a new field with the following information:
   - Scope: **private**
   - Type: **RestaurantContext**
   - Name: **_context**

5.  Add a constructor with the following parameter:
    - Parameter: 
        - Type: **RestaurantContext** 
        - Name: **context**

6. In the **RestaurantBranchesController** constructor, initialize the **_context** field with the value of the **context** parameter.

7. Add a method for the **Get** action with the following information:
   - Scope: **public**
   - Return type: **ActionResult	&lt;List&lt;RestaurantBranch&gt;&gt;**
   - Name: **Get**

8. Annotate the **Get** action with the **HttpGet** attribute.

9. In the **Get** method, create a variable named **branches** of type **var** and assign it the value of the following LINQquery:

   - From: **r in _context.RestaurantBranches**
   - Orderby: **r.City**
   - Select: **r**
   
10. Return the **List&lt;RestaurantBranch&gt;** result using the **branches.ToList** method. 


#### Task 2: Run the application

1. Save all the changes.

2. In Solution Explorer, right-click **Server**, and then click **Set as StartUp Project**.

3. Start the application without debugging.
    >**Note:**  The browser displays the first restaurant in **JSON** format.

4. Close **Microsoft Edge**.

#### Task 3: Add an action that gets a parameter to a Web API application

1.  Create a new controller with the following information:
   - Controller name: **ReservationController**
   - Template: **API Controller - Empty**
   - Folder: **Controllers**
   
2. In the **ReservationController** class, add **using** statements for the following namespaces:
   - **Server.Data**
   - **Server.Models**
   
3. Create a new field with the following information:
   - Scope: **private**
   - Type: **RestaurantContext**
   - Name: **_context**

4.  Add a constructor with the following parameter:
    - Parameter: 
        - Type: **ReservationController** 
        - Name: **context**

5. In the **ReservationController** constructor, initialize the **_context** field with the value of the **context** parameter.

6. Add a method for the **GetById** action with the following information:
   - Scope: **public**
   - Return type: **ActionResult&lt;OrderTable&gt;**
   - Name: **GetById**
   - Parameter: 
        - Type: **int** 
        - Name: **id**

7. Annotate the **GetById** action with the **HttpGet** attribute.

8. In the **GetById** method, create a variable named **order ** of type **var** and assign it the value of **_context.ReservationsTables.FirstOrDefault(p => p.Id == id)**.

9. Create an **IF** statement that checks that the value of the **order** varible is **null**. 

10. Inside the **IF** statement code block, return a **NotFoundResult** result using the **NotFound** method.

11. After the **IF** statement code block, return the **ActionResult&lt;OrderTable&gt;** result usig the **order** variable.

#### Task 4: Run the application

1. Save all the changes.

2. Start the application without debugging.

3. In **Microsoft Edge**, navigate to **http://localhost:[port]/api/Reservation/1**.
    >**Note:**  The browser displays the first restaurant in **JSON** format.

4. Close **Microsoft Edge**.


#### Task 5: Add a Post action to a Web API application

1. In the **ReservationController** constructor, add a method for the **GetById** action with the following information:
   - Scope: **public**
   - Return type: **ActionResult&lt;OrderTable&gt;**
   - Name: **Post**
   - Parameter: 
        - Type: **OrderTable** 
        - Name: **orderTable**
        
2. Annotate the **Post** action with the **HttpPost** attribute.

3. Create an **IF** statement that checks that the value of the **ModelState.IsValid** varible is **false**. 

4. Inside the **IF** statement code block, return a **BadRequestResult** result using the **BadRequest** method. Pass the **ModelState** property as a parameter to the **BadRequest** method.

5. After the **IF** statement code block, call the **Add** method of the **_context** field. Pass the **orderTable** property as a parameter to the **Add** method.

6. Call the **SaveChanges** method of the **_context** field. 

7. Return the **ActionResult&lt;OrderTable&gt** result usig the **CreatedAtAction** method. Pass **nameof(GetById)**,  **new { id = orderTable.Id }** and orderTable asparameters to the **CreatedAtAction** method.

>**Results** : After completing this exercise, you will be able to

### Exercise 2: 

#### Scenario

After...

The main tasks for this exercise are as follows:

1.	

2.	

3.	

4.

5.	

6.	

7.

#### Task 1: 

1. 

#### Task 2: 

1. 

#### Task 3: 

1. 

#### Task 4: 

1. 

#### Task 5: 
1. 

#### Task 6: 
1. 

#### Task 7: 

1. 

### Exercise 3: 

#### Scenario

After..

The main tasks for this exercise are as follows:

1.	

2.

3.	

#### Task 1: 

1. 

#### Task 2: 


#### Task 3: 


>**Results** : After completing this exercise, alongside testing, you have developed a functional MVC Application.

>**Results** :  At the end of this exercise, you will be able to add logging in different logging levels in different environments, displaying errors or information by writing into a log file or a console output in a desired format, and creating a mock substitute using a mocking framework.

©2018 Microsoft Corporation. All rights reserved.

The text in this document is available under the  [Creative Commons Attribution 3.0 License](https://creativecommons.org/licenses/by/3.0/legalcode), additional terms may apply. All other content contained in this document (including, without limitation, trademarks, logos, images, etc.) are  **not**  included within the Creative Commons license grant. This document does not provide you with any legal rights to any intellectual property in any Microsoft product. You may copy and use this document for your internal, reference purposes.

This document is provided &quot;as-is.&quot; Information and views expressed in this document, including URL and other Internet Web site references, may change without notice. You bear the risk of using it. Some examples are for illustration only and are fictitious. No real association is intended or inferred. Microsoft makes no warranties, express or implied, with respect to the information provided here.