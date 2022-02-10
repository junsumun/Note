# Heroku

## Node.js
### Set up
  1. Install Heroku using Homebrew
  ```
  brew install heroku/brew/heroku
  ```
  2. Login using Heroku CLI
  ```
  heroku login
  ```
  3. Clone a git project
  ```
  git clone <git project>
  ```
  
  Note: Heorku assigns a port number
  ```
  const PORT = process.env.PORT || 5000;
  ```
  
### Deploy the app
  1. Create a heroku app
  ```
  heroku create
  ```
  2. Push node.js app to heroku
  ```
  git push heroku main
  ```
  3. Open the application
  ```
  heroku open
  ```
  
## Issues

Application deployed to Heroku is not accessible.
| # | Title | Description | Status | References | Solution |
| - | ----- | ----------- | ------ | ---------- | -------- |
| 1 | Herkoku app not accessible | Node.js application is deployed as a heroku application by using ```git push heroku main``` but the application is not accessible. | Resolved |[Heroku Deploy the app](https://devcenter.heroku.com/articles/getting-started-with-nodejs#deploy-the-app) | Heroku assigns its own port number thus, we need to write our port listner dynamically. [Solution code](#issue-1-solution-code)

### Issue 1 solution code
```javascript
  // before
  const PORT = 5000;
  
  app.listen(PORT, () => {
    console.log(`Server listening on port ${PORT}`);
  });
  
  // after
  const PORT = process.env.PORT || 5000;
  
  app.listen(PORT, () => {
    console.log(`Server listening on port ${PORT}`);
  });
```
