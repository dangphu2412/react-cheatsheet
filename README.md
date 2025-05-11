# React Cheatsheet

## React Element

- This is the smallest unit of react
- Is a javascript object that building pieces of **virtual DOM**
- We can create a React Element by: `React.createElement('div')`
```javascript
// Detail log structure of React.createElement('div')
const element = {
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
        props: {params: [Promise], searchParams: [Promise]},
        debugStack: [Error],
        debugTask: {run: [Function]}
    },
}
  
// For render a list of children
function Page() {
  return React.createElement('div', {}, [
      React.createElement('p', {}, ['Content'])
  ])
}
```
- Or we can use JSX syntax to simply use React Element:
```jsx
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
```jsx
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

- So when we build a ton of Element to construct the UI, this looks like a mess? How do we maintain this long lines of code?

## React Component
- Component definition born to solve this problem.
- React [said](https://react.dev/learn/your-first-component) it can be a function accept arbitrary inputs (props) and return React Elements describing what should we show on the UI or a class, ...
- We can think of it as **an object** in UI, object then we construct with inputs
```typescript jsx
type BookFilterProps = {
    search: string;
    bestSellerFilter: boolean;
};

function BookFilter({ search, bestSellerFilter }: BookFilterProps) {
  return <div>
    <input name={'search'} value={search} />
    <input name={'best-seller-filter'} type={'radio'} value={bestSellerFilter} />
  </div>
}
```
- So usually, we see an object have their own state, human can be angry, sad, ...etc. component is so on.
## State
- Yes, it is component memory, their state.
- Let's think of it as object
```typescript jsx
function BookFilter() {
  const [search, setSearch] = useState('');
  const [isBestSeller, setIsBestSeller] = useState(false);
  
  return <div>
    <input name={'search'} value={search} onChange={setSearch} />
    <input name={'best-seller-filter'} type={'radio'} value={isBestSeller} onChange={setIsBestSeller} />
  </div>
}
```
- So the book filter can have their own memory, when we change search characteristic, we change best seller radio filter, ...etc.