# Concept

- Store
- Actions
- Immutability
- Reducers

+++

# Store
-It's where stay every shared information.

+++
### Example - Store
```js
const store = {
   Books: [
        {
          id: "0",
          name: "1984",
          read: true
        },
        {
          id: "1",
          name: "Handmaid's tale",
          read: false
        },
        {
          id: "2",
          name: "Jurassic world",
          read: true
        }
      ],
};
```

+++
### Actions
- Action is object
- There is always a type field
- It's start point(**request**) to change a store
```js
{
    type: 'ADD_TODO',
    title: 'Nuevo name'
}
```
+++
#### Action Creator - Real World
- It's a action inside a function
```js 
function addTodo(title) {
    return {
        type: 'ADD_TODO',
        title: title
    }
}
```
+++

# Immutability

- It's a concept from functional programing
- It's more simple to compare reference than compare every field.
- Think about nested struct(object or array)


+++
# Nested struct
![Nested struct](https://i.stack.imgur.com/OGmJJ.png)

   
+++
# Reducers 
Where things happened 
+++
#### Reducers - Example
```js

function todos(state = [], action) {
  switch (action.type) {
    case 'ADD_TODO':
      return [
        ...state,
        {
          title: action.text,
        }
      ]
    default:
      return state
  }
}

```
---

# Single Source of Truth


```js
  dispatch({type: 'action'})=> reducer => store
```
---

# PlayTime 

 Go to https://stackblitz.com/edit/redux-xp