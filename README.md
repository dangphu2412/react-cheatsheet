# React Cheatsheet

## React Element

- This is the smallest unit of react
- Is a javascript object that building pieces of **virtual DOM**
- We can create a React Element by: `React.createElement('div')`
```javascript
// Detail log structure of React.createElement('div')
{
  '$$typeof': Symbol(react.transitional.element),
  type: 'div',
  key: null,
  props: {},
  _owner: {
    name: 'LoginPage',
    env: 'Server',
    key: null,
    owner: null,
    stack: [],
    props: { params: [Promise], searchParams: [Promise] },
    debugStack: [Error: react-stack-top-frame],
    debugTask: { run: [Function: run] }
  }
  
// For render a list of children
function Page() {
  return React.createElement('div', {}, [
      React.createElement('p', {}, ['Content'])
  ])
}
}
```
- Or we can use JSX syntax to simply use React Element:
```javascript
function Page() {
  return <div>
      <p>Content</p>
  </div>
}
```