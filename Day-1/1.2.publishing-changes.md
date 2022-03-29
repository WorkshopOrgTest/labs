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
