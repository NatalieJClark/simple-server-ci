# Simple Server CI/CD

## Introduction

- I made this project for Makers Module 5 - Cloud Deployment: Shipping CI/CD
- This is a simple web server that serves a single route.
- It shows the user a `Hello, world!` message.
- It is containerised with Docker using the `Dockerfile`.
- It uses Exoframe (Maker's toy cloud hosting system) to deploy to the cloud.
- It uses [GitHub Actions](https://docs.github.com/en/actions) to set up CI/CD with the config file `.github/workflows/main.yml`.
- A generated Exoframe deployment token is used to grant permission to deploy.

## Objectives

I used this project to learn to:
- [x] Explain what continuous integration is and why it is used.
- [x] Explain what continuous deployment is and why it is used.

## Setup

To set up this project:

```bash
# Clone this repo
; pipenv install
; pipenv shell
; pytest           # Run the tests
; python app.py    # Run the server
```
To practise CI-CD workflow:
```bash
# 1. Create a new branch in your local repository.
; git checkout -b your-branch-name

# 2. Make some changes to make a test fail.

# 3. Commit and push those changes to a remote branch.
; git add .
; git commit -m "commit message"
; git push -u origin your-branch-name

# 4. Create a pull (merge) request
  # - When you push your changes it will give you a link to submit a pull request.
  # - Or, open up this repository and look for the 'Pull Requests' tab. There should be a notice in there.
  # - Or you can create a new PR for your branch with the big green button.

# 5. See that the build has failed and you'll need to fix your failure:
  # a) Fix the failure.
  # b) Commit the fix.
  # c) Push the fix (to the same branch).

# 6. See the PR update, the build run and pass.

# 7. Merge the changes.

# 8. See the workflow pass on the main branch after integration.
```
