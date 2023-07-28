# Types of Components
### 1. Functional Components:

**Details:** 
- Functional components are the simplest type of components in React.
- They are stateless and written as regular JavaScript functions.
- They receive props as their arguments and return JSX elements to render UI.

**Significance:** 
- Functional components promote code simplicity and reusability.
- Since they don't handle state or lifecycle methods, they are easy to read, write, and test.
- They are the recommended choice for presentational components that focus on rendering UI based on props.

```jsx
// Functional Component Example: Header
const Header = () => {
  return <h1>Todo App</h1>;
};

// Functional Component Example: TodoItem
const TodoItem = ({ todo }) => {
  return <div>{todo.title}</div>;
};

// Functional Component Example: TodoList
const TodoList = ({ todos }) => {
 ...
};

// Functional Component Example: AddTodo
const AddTodo = () => {
  ...
};

// Functional Component Example: TodoContainer
const TodoContainer = () => {
...
};
```

### 2. Class Components:

**Details:** 
- Class components are stateful and extend the `React.Component` class.
- They include the `render()` method, where the JSX representation of the component's UI is defined.

**Significance:** 
- Class components are essential when you need to manage state, handle lifecycle methods, or use advanced features like context and refs.
- They allow you to use React's state management system and lifecycle hooks for more complex components.

```jsx
// Todo Container Component Example (Class Component)
class TodoContainer extends React.Component {
  state = {
    todos: [],
  };

  // Function to add a new todo to the list of todos
  addTodo = (newTodo) => {
    this.setState((prevState) => ({
      todos: [...prevState.todos, newTodo],
    }));
  };

  render() {
    const { todos } = this.state;

    return (
      <div>
        <Header />
        <TodoList todos={todos} />
        <AddTodo onAddTodo={this.addTodo} />
      </div>
    );
  }
}

export default TodoContainer;
```

### 3. Component with Descriptive Names:

**Details:** 
- Descriptive names are used to give a clear and concise idea of the component's purpose.
- They often use meaningful nouns or noun phrases related to the component's functionality.

**Significance:** 
- Descriptive names significantly improve code readability and maintainability.
- When other developers encounter the component name, they can quickly understand its purpose without needing to inspect the component's code.

```jsx
// Descriptive Component Example: TodoList
const TodoList = ({ todos }) => {
  return (
    <div>
      <h2>Todo List</h2>
      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>
            <TodoItem todo={todo} />
          </li>
        ))}
      </ul>
    </div>
  );
};
```

### 4. Component for Reusable Elements:

**Details:** 
- Components that represent reusable elements like buttons, input fields, etc., should have more generic and abstract names.
- The names should convey the element's nature and use case.

**Significance:** 
- Creating reusable components helps reduce code duplication and ensures consistent UI elements throughout the application.
- It simplifies maintenance and updates when you need to make changes to these elements.

```jsx
// Reusable Button Component Example
const Button = ({ onClick, children }) => {
  return <button onClick={onClick}>{children}</button>;
};

```

### 5. Presentational Components:

**Details:** 
- Presentational components are solely responsible for the UI and should not handle complex logic.
- They receive data from props and display it without any business logic.

**Significance:** 
- Separating UI concerns from logic improves code modularity and makes components easier to test and maintain.
- Presentational components are easier to understand and reuse, as they focus solely on rendering UI elements based on data.

```jsx
// Presentational Component Example: TodoItem
const TodoItem = ({ todo }) => {
  return (
    <div>
      <input type="checkbox" checked={todo.completed} />
      <span>{todo.title}</span>
    </div>
  );
};
```

### 6. Container Components:

**Details:** 
- Container components manage the logic and data flow for their child components.
- They often encapsulate business logic, handle data fetching, and provide data to presentational components through props.

**Significance:** 
- Container components help achieve separation of concerns by separating data management from UI rendering.
- They make the codebase more maintainable and scalable, as you can have multiple presentational components using the same container component to manage data.

```jsx

// Todo Container Component Example (Functional Component)
import React, { useState } from 'react';

const TodoContainer = () => {
  const [todos, setTodos] = useState([]);

  // Function to add a new todo to the list of todos
  const addTodo = (newTodo) => {
    setTodos((prevTodos) => [...prevTodos, newTodo]);
  };

  return (
    <div>
      <Header />
      <TodoList todos={todos} />
      <AddTodo onAddTodo={addTodo} />
    </div>
  );
};

export default TodoContainer;
```

### 7. Higher-Order Components (HOC):

**Details:**
- Higher-Order Components are functions that take a component as input and return an enhanced version of that component.
- They wrap the input component with additional functionality.

**Significance:** 
- HOCs enable code reuse and cross-cutting concerns.
- They allow you to add functionalities like authentication, logging, and error handling to multiple components without modifying their original implementations.

```jsx
// Higher-Order Component (HOC) Example (Functional Component)
const withAuth = (WrappedComponent) => {
  const AuthenticatedComponent = (props) => {
    // Add authentication logic here
    const isAuthenticated = true;

    return isAuthenticated ? (
      <WrappedComponent {...props} />
    ) : (
      <p>Please login to access this component.</p>
    );
  };

  return AuthenticatedComponent;
};

// Usage of the HOC with a functional component
const MyComponent = () => <div>My Component Content</div>;
const AuthenticatedComponent = withAuth(MyComponent);
```

### 8. Component with Compound Names:

**Details:** 
- Components with compound names use multiple words, following the PascalCase convention, to create a clear and expressive name for complex components.

**Significance:** 
- Using compound names improves code clarity and makes it easier to understand the component's functionality.
- It helps other developers quickly identify the component's role and intent.

```jsx
// Complex Component Example
// Functional Component Example: TodoItem
const TodoItem = ({ todo }) => {
  return <div>{todo.title}</div>;
};

// Functional Component Example: TodoList
const TodoList = ({ todos }) => {
 ...
};

// Functional Component Example: AddTodo
const AddTodo = () => {
  ...
};

// Functional Component Example: TodoContainer
const TodoContainer = () => {
...
};
```


## Todo app example.
```jsx
import React, { useState } from 'react';

// Functional Component Example: Header
const Header = () => {
  return <h1>Todo App</h1>;
};

// Functional Component Example: TodoItem
// Presentational Component Example: TodoItem
const TodoItem = ({ todo }) => {
  return (
    <div>
      <input type="checkbox" checked={todo.completed} />
      <span>{todo.title}</span>
    </div>
  );
};

// Functional Component Example: TodoList
const TodoList = ({ todos }) => {
  return (
    <div>
      <h2>Todo List</h2>
      <ul>
        {todos.map((todo) => (
          <li key={todo.id}>
            <TodoItem todo={todo} />
          </li>
        ))}
      </ul>
    </div>
  );
};

// Functional Component Example: AddTodo
const AddTodo = ({ onAddTodo }) => {
  const [newTodo, setNewTodo] = useState('');

  // Function to handle input change for new todo
  const handleInputChange = (event) => {
    setNewTodo(event.target.value);
  };

  // Function to add a new todo
  const handleAddTodo = () => {
    if (newTodo.trim() === '') {
      return; // Prevent adding empty todos
    }

    onAddTodo({
      id: Date.now(), // Using current timestamp as id (for simplicity)
      title: newTodo,
      completed: false,
    });

    setNewTodo('');
  };

  return (
    <div>
      <input type="text" value={newTodo} onChange={handleInputChange} />
      <button onClick={handleAddTodo}>Add Todo</button>
    </div>
  );
};


// // Todo Container Component Example (Functional Component)
import React, { useState } from 'react';

const TodoContainer = () => {
  const [todos, setTodos] = useState([]);

  // Function to add a new todo to the list of todos
  const addTodo = (newTodo) => {
    setTodos((prevTodos) => [...prevTodos, newTodo]);
  };

  return (
    <div>
      <Header />
      <TodoList todos={todos} />
      <AddTodo onAddTodo={addTodo} />
    </div>
  );
};

export default TodoContainer;


// Todo Container Component Example (Class Component)
class TodoContainer extends React.Component {
  state = {
    todos: [],
  };

  // Function to add a new todo to the list of todos
  addTodo = (newTodo) => {
    this.setState((prevState) => ({
      todos: [...prevState.todos, newTodo],
    }));
  };

  render() {
    const { todos } = this.state;

    return (
      <div>
        <Header />
        <TodoList todos={todos} />
        <AddTodo onAddTodo={this.addTodo} />
      </div>
    );
  }
}

export default TodoContainer;

```


