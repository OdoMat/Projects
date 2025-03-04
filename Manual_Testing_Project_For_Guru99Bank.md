<h1>GURU99 BANK</h1>

The scope of the final project for ITF Manual Testing Course is to use all gained knowledge throught the course and apply them in practice, using a live application

Application under test: **Guru99 Bank**

Tools used: Jira, Zephyr Squad.

<h2>Functional specifications:</h2>

The below stories was created in Jira and describes the functional specifications of the "**Guru99 Bank Manager Role**" module, for which the final project is performed upon.  

**[Stories.pdf](https://github.com/user-attachments/files/17367935/Stories.pdf)**

Here you can find the release that was created for this project:

**![release](https://github.com/user-attachments/assets/0be4e712-76ac-4b4f-b273-b9f742609768)**


<h2>Testing process</h2>

The test process was performed based on the standard test process as described below.

<h3>1.1 Test planning</h3>

The Test Plan is designed to describe all details of testing for all the modules from the Guru99 Bank application.

The plan identifies the items to be tested, the features to be tested, the types of testing to be performed, the personnel responsible for testing, the resources and schedule required to complete testing, and the risks associated with the plan. The test plan that was created for this project can be found here:  
**[Guru99 Test Plan.pdf](https://github.com/user-attachments/files/17368010/Guru99.Test.Plan.pdf)**


<h4>1.1.1. Roles asigned to the project and persons allocated</h4>

<ul>
  <li>Project manager: Andrew Garfield</li> 
  <li>Product owner: John Smith</li>
  <li>Software developer: Julia Adams</li>
  <li>QA Engineer: Odorhean Mateut Cristian</li>
</ul>

<h4> 1.1.2 Entry criteria defined </h4>

**- Testing environment is up and running.**    
**-	Business requirements are completed by the analysis team and are delivered to the appropriate testing team for evaluation.**    
**-	Potential project risks are detected and mitigated.**    
**- Roles and responsibilities are allocated.**    
**-	Test plan should be finalized before entering the next phase of testing.**    
**-	Define the objectives of testing and the accepted level of quality.**  


<h4> 1.1.3 Exit criteria defined </h4>

**- 90% or more of the tests are passed.**    
**-	No critical issues have status open.**    
**-	All detected errors have been reported and closed.**    
**-	The budget was reached.**    
**-	The deadline was reached.**    
**-	The objectives were fulfilled.**  
**-	The product usage documentation has been finalized with the scenarios evaluated during the testing phase.**   
**-	Test completion report has been created and sent to the stakeholders.**      
**-	Product risks have been identified and mitigated.**   

<h4> 1.1.4 Test scope</h4>

<h5> Tests in scope: </h5>

**- New Customer Module - Make sure that a manager can succesfully add a new customer.**  
**- Edit Customer Module - Make sure that a manager can successfully edit details like address, email, telephone of a customer.**    
**- Delete Customer Module - Make sure a manager can successfully delete a customer.**    
**- New Account Module-- Make sure a manager can add a new account to an existing customer.**    
**- Edit Account Module - Make sure a manager can add and edit account details for an existing account.**    
**- Delete Account Module - Makee sure a manager can delete an account for an existing customer.**    
**- Deposit Module - Make sure a manager can deposit money into any account.**    
**- Withdraw Module - Make sure a manager can withdraw money from any account.**    
**- Fund Transfer Module - Make sure a manager can transfer funds from any source bank account to destination account.**    
**- Balance Enquiry Module - Make sure a manager can view balance of all the customers who come under his supervision.**    

<h5>Tests not in scope: </h5>

**-	No QA support for mobile applications developed. Only web applications will be tested.**  
**-	Automation testing is beyond scope.**  
**-	Non-functional testing like performance (stress testing, load testing, volume testing, scalability testing, spike testing) and security is beyond the scope of this project.**  
**-	These futures are not to be tested: User Interfaces, Hardware Interfaces, Software Interfaces, Comunications Interface, Database Logical, Website Security and Performance.**  

<h4>1.1.5 Risks detected</h4>

<h5>Project risks:</h5>

**-	The team does not have the proper knowledge or experience in order to guarantee the desired level of quality for the application.**  
**-	Limited availability of key team members could delay the project.**  
**-	Not enough time has been allocated in order to properly test and cover all the functionalities in scope.**  
**-	Non-Functional testing such as sterss testing, load testing,scalability testing, spike testing etc, are beyond the project scope, which might lead to unidentified issues in these areas.**  


<h5> Product risks: </h5>

**-	All the data that is going to be used will be test data, which will not give us an experience of the application close enough to the ones that the user will experience.**  
**-	Potential defects in functionalities such as fund transfers, balance enquiries and cusmomer management, might lead to incorrect transactions or data loss.**  
**-	Many users may not have adequate computer knowledge, leading to usability issues.**   
**-	The software is only compatible with Chrome version 27 and above, this could cause issues.**    
**-	The system might have security vulnerabilities, especialy with functionalities like fund transfer and password management.**  
**-	The banking software must comply with financial regulations. Any non-compliance could lead to legal issues.**


<h4>1.1.6 Evaluating entry criteria</h4>

The entry criteria defined in the Test Planning phase have been achieved and the test process can continue.

<h3>1.2 Test Monitoring and Control<h3>

In this project, the Monitoring and Control Phase was essential because it allowed me to ensure that each feature was functioning as intended and that any issues were quickly identified and resolved. The Monitoring and Control Phase is crucial in software testing as it ensures that the project stays aligned with its goals, quality standards, and timeline. 
Below you can find the Test Status Report from zephyr.  

![Test Metrics](https://github.com/user-attachments/assets/7624c472-5ead-4d62-9bed-758d15cc590a)  

![Test Executions by test cycle](https://github.com/user-attachments/assets/ddf4362f-5a7f-45b1-9258-b10142bd21f0)  


<h3> 1.3 Test Analysis </h3>
The testing process will be executed based on the application requirements.</b>. <br><br>

The following test conditions were found: <br>

![Tests 1](https://github.com/user-attachments/assets/02aed150-52ee-4ee5-a2b9-0823804b6f48)
![Tests 2](https://github.com/user-attachments/assets/49cda4fa-854b-45d6-bfd8-64436d402bcc)
![Tests 3](https://github.com/user-attachments/assets/c4733b01-6848-486c-9b73-71d77c730489)

<h3>1.4 Test Design</h3>

Functional test cases were created in Zephyr Squad based on the analysis of the specifications. The test cases can be accessed here **[Test Cases.xlsx](https://github.com/user-attachments/files/17378259/Test.Cases.xlsx)**


<h3>1.5 Test Implementation</h3>

The following elements are needed to be ready before the test execution phase begins:

**-We make sure that all the test data is available and reviewed.**  
**-	We make sure that the setup environment is up and running.**  
**-	We make sure that we have all the needed access and permissions to all the systems involved in the validation process.**  
**-	We prioritize the tests based on risks and business priority.**  

<h3>1.6. Test Execution </h3>

Test cases are executed on the created test Cycle summary: **Version 1**

Bugs have been created based on the failed tests. The complete bug reports can be found here: **[Bugs.pdf](https://github.com/user-attachments/files/17378313/Bugs.pdf)**  

The following is a summary of the bugs that have been found  

![Bugs Severity and Priority](https://github.com/user-attachments/assets/5620e436-51bb-4534-b71a-9fb16d10ec5e)


Full regression testing is needed on the impacted areas after the bugs are fixed and retesting will be done for every functionality that was previously failed.

<h3> 1.7 Test Completion</h3>
As the Exit criteria were met and satisfied as mentioned in the appropriate section, this feature is suggested to ‘Go Live’ by the Testing team

The traceability matrix was generated and can be found here: [Traceability Matrix.xlsx](https://github.com/user-attachments/files/17400810/Traceability.Matrix.xlsx)

Test execution chart was generated and can be found below.  

![Test Execution by cycle](https://github.com/user-attachments/assets/41d5e03c-5c6e-446c-864a-1b1fd288c717)

The final report shows that a number **16** tests have failed of a total of **24**

A number of **13** total bugs were found, from which the priority is: **5** are high and **8** are medium.

**In this project, I created and executed a total of 24 tests, covering approximately 60% of the functionalities within the project scope. The testing primarily focused on the critical functionalities of the application from the manager's perspective. During the testing process, I identified 12 bugs. These include data validation issues in the fields for email, passwords, dates of birth, and character limitations. Most of the defects are validation problems that could be fixed without significantly impacting the overall functionality. For this reason, I do not believe the identified bugs will affect the product's release to production, but I recommend addressing them before launch, as they could affect user experience and data integrity. The application's limited compatibility with only certain browser versions may negatively impact user experience and its accessibility. I recommend extending support for other browser versions before the release.**
