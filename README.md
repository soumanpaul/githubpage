# Deploying React Applications to Github Pages

```
Install the gh-pages from npm. In the terminal, run:
npm install gh-pages or yarn add gh-pages This package would help us to create a gh-pagesbranch on Github and also serve our bundled react files on the branch.

Locate the package.json file in your root directory, add this line of code to your script: "homepage": "link-to-your-repository", and save. In my own case it would look like this:

{
"name": "jv",
"version": "0.1.0",
"private": true,
"homepage": "https://seunzone.github.io/TD-React-Challenge-Test-1",
...
}


Note: If you are linking your domain name to your Github pages, this line would be a little different, it should be: "homepage": "your-custom-domain"
```

```
In your package.json file, locate “scripts” add these lines of code:

{

"predeploy": "yarn run build",
"deploy": "gh-pages -d build",

}
```


```

So your "scripts"should look like this:

"scripts": {
"start": "react-scripts start",
"predeploy": "yarn run build",
"deploy": "gh-pages -d build",
"build": "react-scripts build",
"test": "react-scripts test",
"eject": "react-scripts eject"
},

```

```
The predeploy command helps bundle the react app whilst the deploy command fires up the bundled file.

In the terminal, run this command npm run deploy OR yarn run deploy. This command pushes your built file to the gh-pagesbranch on your remote repository
```

```
Note: 
Sensitive information (eg .env files) should not be pushed to your online repository. My workaround is usually to git ignore the .env or config file before pushing to my remote repository, when this is done I then allow git to track the .env or config file before running yarn run deploy, this makes my deployed app to have access to the necessary configuration files I need without compromising the security of the app.

```