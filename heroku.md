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
  
  
