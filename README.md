## Getting started with redux for beginner
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



### 1. create Store
```
import { createStore } from "redux";
import productReducer from "./reducers/productReducer";

const store = createStore(productReducer);
export default store;
```



### 2. create a reducer folder
create a reducer folder in redux folder and create file named productReducer or any other name match to the activity of the reducer. here the name is `productReducer`, inside this file code example are give below,
```
import { ADD_TO_CART, REMOVE_FROM_CART } from "../actionTypes/actionTypes";

const initialState = {
    cart: []
};

const productReducer = (state = initialState, action) => {
    switch (action.type) {
        case ADD_TO_CART:
            return {
                ...state,
                cart: [...state.cart, action.payload]
            }
        case REMOVE_FROM_CART:
            return {
                ...state,
                cart: [...state.cart, action.payload]
            }
        default:
            return state;
    }
}

export default productReducer;
```




### 3. create an actionTypes folder
create a folder named `actionTypes` where you can define a file called `actionTypes.js` where some action can be defined. according to them `dispatch()` function can dispatch an action. 

```
export const ADD_TO_CART = "ADD_TO_CART";
export const REMOVE_FROM_CART = "REMOVE_FROM_CART";
```



### 4. create an actionCreators folder
create an actionCreators folder where you can define what action to do and the logic of the action object that mainly get from a dispatch function as an object. so in the actionCreators here we create a `productAction.js` file

```
import { ADD_TO_CART } from "../actionTypes/actionTypes"

export const addToCart = (product) => {
    return {
        type: ADD_TO_CART,
        payload: product,
    }
}
```
use this `addToCart(product)` directly inside the dispatch function. 
```
        <button onClick={() => { dispatch(addToCart(product)) }}>
          Add to cart
        </button>
 ```
 



