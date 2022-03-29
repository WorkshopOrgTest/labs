# 1.2 Publishing new changes to repository

## Task 1 - Create a Branch in Local Environment [15 minutes]

- Create a new Dev Branch
- Add your Changes 
- Commit and Publish to GitHub

<details>
    <summary>Solution</summary>
    
  ```shell
  $ git checkout -b Dev # Add New File or change exisiting File
  $ git add .
  $ git commit -m "New Changes Added #[Issue_NUmber]"
  $ git push --set-upstream origin
  ```
</details>

# Task 2 - Create a Branch Rule [20 minutes]
By now your repository at GitHub has content and we can now protect our branches against unwanted direct updates. This is a very common setup in the enterprise.
In this excursive we will create a branch rule that prevents you to commit to the main branch direct and require you to create a pull request.

In your GitHub repo go to the settings tab and click the branches option as shown here:


![image](https://user-images.githubusercontent.com/67369513/160524278-a49275b7-c677-460e-bbe8-642e2c38b87e.png)


Now add a new rule and define which branch you want to protect. e.g. provide the pattern name `main`
Next you select the following options:
1. `Require pull request reviews before merging`
2. `Include administrators`

Now save this Branch Rule and see if it works.

To check if it works, create a change on one of the files that is in the main branch. Just use the portal to make the change and verify that the moment you want to commit the change you see the below indicator that you need to create a new branch before you can commit:

![image](https://user-images.githubusercontent.com/67369513/160524333-95970e32-b764-45b5-9dfd-575944a4fdb2.png)

Now, create a new branch and create a pull request that enables the code review from someone else in your organization/repository.

# Enforce CODEOWNERS review

If you want to enforce certain teams can only approve parts of the codebase, like a web development team for all the web application code and a docs team for the documentation, you can use the code owners file. We can enforce the code owners need to be part of the review process by adding this to the Branch Protection Rule.
There is already a CODEOWNERS file in the repo that you migrated. It has the following contents:

```
# Example, any change in this repo 
# will require approval from @username
# * @username

# Any change inside the `/Pages` directory
# will require approval from anyone in the organization fluentbytes and the team docsteam
# /Pages @username
# Create your own rules below this line without the # sign
```
Now change the file so it defines the folder `/Pages` has a user as the owner. 

After setting up the file, commit it to the main branch.
Next go to the branch protection rules and for the main branch select the option `Require review from Code Owners`

Save the branch protection rule and make a change to e.g. the startup.cs file and see if you can commit the changes to the main branch. Ask one of the other attendees to review the pull request you created and see if it then is allowed to approve and merge the pull request. Please use the teams chat to find a colleague who can approve your pull request. If you can't find anyone, ask the instructors. 
