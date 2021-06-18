# Software Requirements

## Vision

- What is the vision of this product?
  - Admin site for the faculty of Code Fellows to use that will control the questions that are fed to our Slackbot. It will also allow users to pull reports on quiz results by student name.  
- What pain point does this project solve?
  - To allow teachers to see how students are doing by pulling reports. This will give them an idea on which categories or topics they may need to adjust in the curriculum. It will also provide an easy way to add questions or edit questions that may no longer be relevant. It will also allow students to track their progress.
- Why should we care about your product?
  - It provides a nice admin portal for Code Fellows faculty to control the quiz Slackbot and reporting.

## Scope (In/Out)

### IN - What will your product do
  
- Describe the individual features that your product will do
  - Login with specified acl/roles
  - Generate list of all questions
    - sort list by topic or difficulty
    - search list by keywords
  - Form that allows user to add / edit questions
  - Form that allows admins to add / edit / delete users
  - Ability to pull reports of quiz results/stats
    - search by student name
  - Ability to pull / export reports in CSV format
  
### IN OR OUT?? 

- Anyone can sign up or specifically have admin only create users

### OUT - What will your product not do

- Admins will not be able add questions in the format of short answer or outside of the existing questions schema
- Questions will not have multiple correct answers
- Form won't have the ability to automatcially perform parsing, regex, code blocks for the users. They will need to make sure they do this to make sure account for special characters or code blocks 

## Minimum Viable Product

- What will your MVP functionality be?
  - Login with specified acl/roles
  - Generate list of all questions
    - sort list by topic or difficulty
    - search list by keywords
  - Form that allows user to add / edit questions
  - Form that allows admins to add / edit / delete users
  - Ability to pull reports of quiz results/stats
    - search by student name
  - Guide page to help users understand how to add questions properly
 
- What are your stretch goals?
  - Generating an accumulated report that the student can request in their convo thread with the slackbot
  - Generating a chart of the overall quiz results
  - Refactor our Slackbot to open up for additional conversation options
 
- What stretch goals are you going to aim for?
  - Creating the chart for the admins

## Functional Requirements

- List the functionality of your product
  - Login with specified acl/roles
  - Generate list of all questions
    - sort list by topic or difficulty
    - search list by keywords
  - Form that allows user to add / edit questions
  - Form that allows admins to add / edit / delete users
  - Ability to pull reports of quiz results/stats
    - search by student name
  - Ability to pull / export reports in CSV format
 

## Data Flow 

- Describe the flow of data in your application. 
  - Front-end: Admin portal
    - Login to hit auth routes on the backend and verify user token information
      - Signup - to automatically store login and provide with bare-bones access until Admin grants additional permissions
    - CRUD actions dependant on where they're at in the site:
      - Read of all questions
      - Create/Update/Delete questions
      - Create/Update/Delete users - admin role only
      - Read quiz results
  - Backend Server: 
   - Using Slack Bot Key to connect to the Slack API
   - Connects to DB for questions and to store responses
  - Slackbot
   - User would call slackbot that connects to the server  


## Non-Functional Requirements 

- Non-functional requirements are requirements that are not directly related to the functionality of the application but still important to the app.
- Pick 2 non-functional requirements and describe their functionality in your application.

- **Documentation** Provide users well written documentation on how to correctly add/change questions, how to pull reports and search by student username(slack). And provide admin a well written guide on adding/updating/deleting users. 
- **Security** We will keep users' quiz results safe so that only Code Fellows faculty will have access to pull. We will also keep login credentials of faculty safe. 
