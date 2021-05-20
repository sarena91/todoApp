# vue_todolist_app

## About
```
A simple ToDo list using Vue.js. 

Utilises:
- Vue CLI
- JSONplaceholder (free fake api)
- Vue router
- Fetch API (GET, POST & DELETE requests)
```
## How it works:
```
On page load, the application is populated with random todos from JSONplaceholder using a GET request.
```
```
New todo items can be added using the text input field and submit button. This sends a POST request to JSONplaceholder.
```
```
The delete button (x) on the right of each line item sends a DELETE request and removes the individual item from the list by filtering it out.
```
```
The checkbox on the left of each item toggles its completed status.
```
```
On reload, the app returns to its initial state.
```

### Note:
```
JSONplaceholder assigns the same id value to every new POST. Therefore, the delete function currently removes all of the new inputs even if the delete button is clicked on one new input.