# ReactJS: BigBrain

### Getting Started
---
To start the application locally:
1. Navigate to **frontend** and **backend** folders separately
2. Run **yarn** to install all the required dependencies
3. Run **yarn start** to start the frontend and backend.
4. ReactJS runs at localhost:3000 into a browser and express runs at localhost:5005

All information generated would be saved into **database.json** locally.


### Auto Testing
#### - Cypress

#### "Happy Path" of an admin

1. Registers successfully
2. Creates a new game successfully
3. Updates the thumbnail and name of the game successfully (yes, it will have no questions)
4. Starts a game successfully
5. Ends a game successfully (yes, no one will have played it)
6. Loads the results page successfully
7. Logs out of the application successfully
8. Logs back into the application successfully

#### Custom testing path
0. Create an account with email as someone@mail
   Fail to do it.
0.5 rectify the error by adding a .com
1. Create a quiz
2. Update the quiz name and thumbnail
3. Add a quiz question
	- 1st question: single choice (no embedded)
	- 2nd question single choice (embedded image)
    - 3rd question multiple choice (embedded YouTube url) (make 6 answers)
	- 4th question multiple choice (no embedded) (3 answers) (correct answer = 1 and 4). Windows.alert should pop up
4. Edit 1st question and make it multiple choice and add an image to it
5. Edit 2nd Question, change time limit to 120. Windows.alert should pop up. make an assertion to capture error.
6. Delete the 2rd question
7. Edit 1st question and try and remove all answers so that there is only 1 answer — Windows.alert should pop up. make an assertion to capture error.
8. Edit 1st question change point to 11000 Windows.alert should pop up. make an assertion to capture error.
9. Delete 1st question.
10. Only 1 question left shown on the screen.

The rationale behind this test is to show that ediiting and modifying a question is done successfully while dynamic renders.
It also shows that a user can modify any field without changing all fields. If a user only wants to change a question image they can do so and it will not affect any other question data. This has been done through multiple layers of validation of the data.

Also, there is multiple error checking when editing a question. For example trying to paste a non youtube URL to the URL embed will result in an error.
Trying to add multiple answers to a single choice question, adding single answer to multiple choice etc.

This test shows that editing a question in any sort of combination of inputs will not cause issues.

#### Component Testing
6 Jests implemented to determine the success of renderness on the page.

### Screenshots
- UI Testing
![Cypress](/screenshot/cypress.png)
- Jest
![Jest](/screenshot/jest.png)