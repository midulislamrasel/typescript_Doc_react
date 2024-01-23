# typescript_Doc_react
# What is typeScript

TypeScript is a programming language that builds on JavaScript by adding a feature called <span style = "color: green" >"Static Typing" </span> This means developers can define the types of variables, making it easier to catch errors during development.
<span style = "color: green" >TypeScript code is converted to JavaScript ,</span>
making it compatible with existing JavaScript projects. It also offers additional features like interfaces, classes, enums, and generics for more structured and maintainable code. Overall, TypeScript provides tools to help developers write better and more reliable code, <span style="color: green">especially in larger projects. </spam>

# Advantages of using TypeScript

##### Static Typing:
TypeScript introduces static typing, allowing developers to define the types of variables. This helps catch errors during development and improves code quality.

##### Early Error Detection:
TypeScript helps catch mistakes in your code before it even runs. By checking for errors during a process called "compile-time," which happens before the code is executed, developers can spot and fix issues early on.Reducing the chances of encountering bugs or unexpected behavior when the program is running.

##### Improved Code Quality:
TypeScript allows developers to specify the types of data in their code. This makes the code clearer, easier to understand, and less prone to mistakes. As a result, the overall quality of the code improves. Additionally, because TypeScript provides a clear structure, it reduces the necessity for extensive comments in the code.

Enhanced IDE Support: TypeScript integrates well with popular code editors, such as Visual Studio Code. This integration provides features like auto-completion, code navigation, and refactoring tools.

##### Object-Oriented Programming Features:
TypeScript supports features like classes, interfaces, and inheritance, making it easier to structure and organize code in an object-oriented manner.

##### Cross-Platform Development:
TypeScript can be used for both client-side (browser) and server-side (Node.js) development, making it versatile for full-stack applications.

## Types Examples


```javascript
type Name: "string"

FullName : Name = "Midul"

 ```

## Array of a type

```javascript
 const name: string[] = ["Midul", "Islam", "Rasel"];
 ```

## Object of a type

```javascript
   type FULLName = {
    names: "string";
    id: number;
    isastudent: boolean;
  };

  const Details: FULLName = {
    names: "Midul Islam",
    id: 1245,
    isastudent: true,
  };
 ```

## Function that doesn't take or return anything

```javascript

onClick: () => void;

 ```

## Function with named prop

```javascript

 onChange: (id: number) => void;

 ```

## Function type syntax that takes an event

```javascript

onChange: (event: React.ChangeEvent<HTMLInputElement>) => void;

 ```

## Alternative function type syntax that takes an event

```javascript
  onClick(event: React.MouseEvent<HTMLButtonElement>): void;
 ```

## Optional Prop
```javascript
type FULLName = {
  name: string;
  isastudent?: boolean;
  
};

const Details: FULLName = {
  name: "good",
};
 ```

## Interfaces and type

##### Interface

when you declare two interfaces with the same name, their definitions are combined or merged into a single interface. This allows you to gradually build up or extend an interface across multiple declarations.

##### Type

if you try to declare two types with the same name, you'll encounter an error.

## Example

```javascript
interface User {
  name: string;
}

interface User {
  age: number;
}
// Merged interface

const user: User = {
  name: "John",
  age: 25,
};
 ```


```javascript
Inderface FULLName = {
names: "string";
id: number;
isastudent: boolean;
};

const Details: FULLName = {
names: "Midul Islam",
id: 1245,
isastudent: true,
};
</code></pre>

# Function Components



```javascript

const App: React.FunctionComponent<{ message: string }> = ({ message }) => (
  <div>{message}</div>

);
 ```

# Hooks

## useState

```javascript
const [state, setState] = useState(false);

 
`state` is Inferred to be a boolean
`setState` only takes booleans
 
 ```
#### TypeScript, when dealing with hooks that have initial values set to <span  style="color:red">null and undefiend</span><span style="color:green"> you can explicitly declare the type and use a union type </span> to allow for both the actual type and null or undefined.

## Example

```javascript
type MyStateType = string | null;
const [myState, setMyState] = (useState < MyStateType) | (null > null);
```

### class Components

```javascript
type GreetProps = {
  age ? : number;
}
class Greet extends React.Components<GreetProps>{
  render(){
    count {age=21} = this.props
  }
}

let el=<Greet age = {3}/>
```

### Events

```javascript
const el = (
  <button
    onClick={(event) => {
      /* event will be correctly typed automatically! */
    }}
  />
);
```

### Context

#### Error Boundaries

### Union Types and Type Guarding

```javascript
{
  count: number | null;
}
```

Type Guarding sometime unio types aolve a problem is one arabut crate another downstream if a and B are both object types, A | B isnt either A or B it is A or B or both at once which causes some confusion if yoy expected it to be the formet learn how to wire checks guards and assertion

### Optional Type

if a component has an optional prop, add a question mark and assign during destructure (or use defaultProps).

```javascript
{
  message?: number;
}

```

### Enum types

A simpler alternative to enums is just declaring a union types of string literals;

```javascript

export declare type Position = "left" | "right" | "top" | "bottom";

```

### Type Assertion

sometime you know better than TypeScript that type using is narrower than it thinks or union types need to be asserted to a more specific type to work with other APIs , so assert with the as key
