# firebase-todolist

- Ref:

https://www.sipios.com/blog-tech/build-a-real-time-todo-app-in-30-minutes-with-reactjs-typescript-and-firebase


## Notes

### create React project *react-todo-list*

npx create-react-app react-todo-list --template typescript

cd react-todo-list

npm start

http://localhost:3000


### Firebase, create project

- create a project named *react-todo-list*

- Plug it to our React app

Now that your Firebase project is created, we need to plug it to our React app! Here is what we are going to do: just select the **</>** web app icon and follow the steps !

- Next step is to actually setup Firebase from your React app. You need to install firebase as a project dependency with *npm install firebase*, then create a firebase.ts file in your src folder to paste the Firebase configuration.

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

20220310: TBC





