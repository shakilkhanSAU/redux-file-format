# redux-file-format

To add redux to an existing project, first of all you need to install `redux` and `react-redux` according to the documentation of [redux] (https://redux.js.org/)

### how to install
```
npm intall redux react-redux
```
or 
```
yarn add redux react-redux
```
after installing you have to create a a folder called `redux` into the `src` folder, and into the `redux` folder create some folder and file according to the file format given to this ripo.

### Store
```
import { createStore } from "redux";
import productReducer from "./reducers/productReducer";

const store = createStore(productReducer);
export default store;
```

### a reducer (create a folder and inside in a file called ____reducer (here porduct reducer)___ 
