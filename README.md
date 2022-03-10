# firebase-todolist

- Ref:

https://www.sipios.com/blog-tech/build-a-real-time-todo-app-in-30-minutes-with-reactjs-typescript-and-firebase


## Setup Project

### create React project *react-todo-list*

npx create-react-app react-todo-list --template typescript

cd react-todo-list

npm start

http://localhost:3000


### Firebase, create project

- create a project named *react-todo-list*

- Plug it to our React app

Now that your Firebase project is created, we need to plug it to our React app! Here is what we are going to do: just select the **</>** web app icon and follow the steps !

- Next step is to actually setup Firebase from your React app. You need to install firebase as a project dependency with *npm install firebase*, then create a **firebase.ts** file in your src folder to paste the Firebase configuration.

```
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSyDqQiFRwl1zwYw4lHJSP9CULROQ21P-HTg",
  authDomain: "react-todo-list-9a62b.firebaseapp.com",
  projectId: "react-todo-list-9a62b",
  storageBucket: "react-todo-list-9a62b.appspot.com",
  messagingSenderId: "922746582509",
  appId: "1:922746582509:web:1c7583c63f0a82f6c263e4"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
```

- If you've checked the Firebase hosting option, the next steps will be about hosting. You will need to run *npm install -g firebase-tools* before enabling hosting.

- This step explains to you how to deploy your application, but this is not mandatory for the moment so let's deploy it later. Feel free to test this functionality, it won't impact the next part of the tutorial.


### Create your first Realtime database

https://react-todo-list-9a62b-default-rtdb.firebaseio.com/


## Coding

### Create records in your database

Remember when you had to paste your firebase configuration in a *firebase.ts* file ? Time to use it!

Just put this line at the end of this file, so you can reuse your configuration wherever needed.

```
export default app;
```

Our database records will be of Todo type. In order to do so, we need to define in a types.ts file:

```
export type Todo = {
  id: string;
  title: string;
  done: boolean;
}
```

npm install react-bootstrap bootstrap@5.1.3


- Upload todos in the database
As you can see, the Form.Control and Button components call two different methods: handleChange and addTodo.

- Read your records from your database
In order to retrieve our todos from the database, we will create a new component TodoList that will retrieve and display the data. In a TodoList.tsx file :

- Update your records
In order to have a fully functional todo list, we need to complete the tasks. Let’s improve the TodoList component by making a checklist. A new changeTodoCompletion function has been added in order to check/uncheck the todos.

## Deploy your application

If you had not done it yet, please install the Firebase CLI with *npm install -g firebase-tools*. You can now run *firebase login* and authenticate to your Firebase account. 

To continue, you may now run *firebase init*. You will be able to manage different features: choose *Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys*.


Once you have selected hosting, you will be asked to chose your project to host: we will use an existing project.

Select your app in the list.


You will now be prompted about Hosting setup. Choose build as the public directory, then agree y to configure single-page app. You can choose to setup automatic builds and deploys with Github but this is not mandatory. If you want to see how to implement it, see you on “To go further” part. 


You can now create your production build with npm run build. Deploy your app with firebase deploy ! 🤩


You now can access your app from your hosting URL, and get more information on your app use on the project console, like check the analytics or chose a custom domain.

To go further : Continuous Deployment (CD)
If you are using a Github repository, you can chose to configure automatic deployment every time new commits are merged on your main branch: this is what we call Continuous Deployment.

To do so, you need to run firebase init and select Hosting: Set up GitHub Actions deploys.

As you already logged in to your Firebase account (if not, run firebase login), you won’t have to do anything for project setup. 

For the GitHub setup, agree to run a build before every deploy. The script to run before every deploy will be npm ci & npm run build. Now you can agree to start a deployment each time a PR is merged. Your GitHub branch associated with your app is usually main.


Once your setup is done, two Yaml files have been created: firebase-hosting-merge.yml and firebase-hosting-pull-request.yml. Commit and push them on your main branch. From your GitHub repository, you can see that a new Actions workflow has been launched!


CD is ready-to-go!





firebase login

firebase init


oopsmails/firebase-todolist


```
albert@albert-mint20:~/Documents/dev/react/firebase-todolist/react-todo-list$ firebase init

     ######## #### ########  ######## ########     ###     ######  ########
     ##        ##  ##     ## ##       ##     ##  ##   ##  ##       ##
     ######    ##  ########  ######   ########  #########  ######  ######
     ##        ##  ##    ##  ##       ##     ## ##     ##       ## ##
     ##       #### ##     ## ######## ########  ##     ##  ######  ########

You're about to initialize a Firebase project in this directory:

  /home/albert/Documents/dev/react/firebase-todolist/react-todo-list

? Which Firebase features do you want to set up for this directory? Press Space to select features, then Enter to confirm your choices. Hosting: Configure f
iles for Firebase Hosting and (optionally) set up GitHub Action deploys

=== Project Setup

First, let's associate this project directory with a Firebase project.
You can create multiple project aliases by running firebase use --add, 
but for now we'll just set up a default project.

? Please select an option: Use an existing project
? Select a default Firebase project for this directory: react-todo-list-9a62b (react-todo-list)
i  Using project react-todo-list-9a62b (react-todo-list)

=== Hosting Setup

Your public directory is the folder (relative to your project directory) that
will contain Hosting assets to be uploaded with firebase deploy. If you
have a build process for your assets, use your build's output directory.

? What do you want to use as your public directory? y
? Configure as a single-page app (rewrite all urls to /index.html)? Yes
? Set up automatic builds and deploys with GitHub? Yes
✔  Wrote y/index.html

i  Detected a .git folder at /home/albert/Documents/dev/react/firebase-todolist
i  Authorizing with GitHub to upload your service account to a GitHub repository's secrets store.

Visit this URL on this device to log in:
https://github.com/login/oauth/authorize?client_id=89cf50f02ac6aaed3484&state=237070972&redirect_uri=http%3A%2F%2Flocalhost%3A9005&scope=read%3Auser%20repo%20public_repo

Waiting for authentication...

✔  Success! Logged into GitHub as oopsmails

? For which GitHub repository would you like to set up a GitHub workflow? (format: user/repository) oopsmails/firebase-todolist

✔  Created service account github-action-468459144 with Firebase Hosting admin permissions.
✔  Uploaded service account JSON to GitHub as secret FIREBASE_SERVICE_ACCOUNT_REACT_TODO_LIST_9A62B.
i  You can manage your secrets at https://github.com/oopsmails/firebase-todolist/settings/secrets.

? Set up the workflow to run a build script before every deploy? Yes
? What script should be run before every deploy? npm ci && npm run build

✔  Created workflow file /home/albert/Documents/dev/react/firebase-todolist/.github/workflows/firebase-hosting-pull-request.yml
? Set up automatic deployment to your site's live channel when a PR is merged? Yes
? What is the name of the GitHub branch associated with your site's live channel? main

✔  Created workflow file /home/albert/Documents/dev/react/firebase-todolist/.github/workflows/firebase-hosting-merge.yml

i  Action required: Visit this URL to revoke authorization for the Firebase CLI GitHub OAuth App:
https://github.com/settings/connections/applications/89cf50f02ac6aaed3484
i  Action required: Push any new workflow file(s) to your repo

i  Writing configuration info to firebase.json...
i  Writing project information to .firebaserc...

✔  Firebase initialization complete!
albert@albert-mint20:~/Documents/dev/react/firebase-todolist/react-todo-list$ 
```
