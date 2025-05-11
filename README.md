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
- So what is JSX? And why it support us writing React so well? Is this a part of React?

## JSX
- Is **JS** and **X** which is **Javascript XML**
- [XML](https://www.w3schools.com/xml/xml_whatis.asp) is eXtensible Markup Language
```xml
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget me this weekend!</body>
</note> 
```
- So JSX is XML for JS, these XML much alike HTML syntax but provide features of XML, writing in JS file
```javascript
function Page() {
    // So we have ability to write HTML like in JS file
    // className="header" is a property functionality of XML
    return <header className="header">
        This is title
    </header>
}
```
- And why it support us writing React so well?
  - Babel compiles JSX down to React.createElement() API
- Is this a part of React?
  - It is not a part of JS also, but React use it from the ground, so, it integrated with React.

