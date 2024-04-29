{:toc}

# Development Task Management

When ad-hoc requests are received from Customers, the team should use DevOps to register any requests there and follow the process defined for Ad-hoc (VAR) projects. If the customer does not have their own Azure DevOps, Jira, or GitHub, the PM should create a new project/backlog in the internal Ciellos Azure DevOps.  

Ad-hoc (VAR) customer request need to be managed by the following process: 
 
1. Customer request is sent to either AS or PM (depending on role responsibility on the project). 
2. AS receives a customer request and creates a new PBI in DevOps. Status on new PBI will be “New”. 
3. AS clarifies details from the customer that should be sufficient for providing estimate of DEV/QA effort and establishing ETA.  
4. Once PBI is ready for the estimation process, AS assigns PBI to TA and change the status to “Ready for Estimate”.  
5. TA analyses requirements and works on estimate. PBI status needs to be changed to “Estimate”.  
6. TA completes the estimates in a proper Excel format and establishes the ETA. TA assign PBI to a PM and change the status to “Ready for Approval”.  
7. PM sends an estimate to the Customer.  
   - If approved, PM changes the PBI status to “Approved” and assigns it TA.  
   - If not approved, PM changes the PBI status to “Not Approved”.

You can see the diagram below that represents all the steps.   
![image.png](./.attachments/.DevOps_Task_Management/image-3a3ef176-2843-4efc-930f-c36192241e79.png) 

According to best practices, the team should have regular planning meetings (once or twice per week), The schedule should be defined by the project rhythm.  

On the planning session, the dev team opens backlog and checks what has been approved and what they can start working on.  

1. The team takes approved PBI one by one and review them.  
2. Dev team together should split PBI to tasks that will be needed to complete the project. The task can be as following:  
   - Design (optional). If dev team decides that information that they have in PBI is not enough and AS should put more clarity and details). If the task is created. It should be assigned to AS.  
   - Development (mandatory). Split PBI to as many development tasks as needed. It should be decided by the team. Assign development task to a developer.  
   - Unit Test (optional). If the project requires unite tests coverage, then task should be mandatory. It should be assigned to developer. 
   - Code review (mandatory). Should be assigned to TA.  
   - Testing in TEST (mandatory). Should be assigned to AS.  
   - Testing in UAT (optional). If the project requires UAT testing, the task should be mandatory. Should be assigned to AS.  
 
   Tasks will have the following statuses “Open”, “In Progress”, “Complete”. 
   - Use “Open” when the task gets created and assigned to a team member.   
   - Use “In Progress” when assigned person started working on it.  
   - Use “Complete”, when assigned person completes the task.  

3. The status of PBIs that have been refined by the team should be changed to ‘In Progress’.  

4. The PBI needs to be assigned to a person who starts working on the first task. Each time when a person completes the task, they need to re-assign PBI to another person who will take care of the next task. 

5. When all tasks are complete, a team member who completed the last task should change the PBI status to “Ready to Deploy” and assigned it to TA.  

6. When TA deploys the PBI to customer side, the PBI status needs to be changed to “Complete” and assigned to PM.  

![image.png](./.attachments/.DevOps_Task_Management/image-77a7e7c1-8dca-4a28-9a7d-a6e2a9696277.png)