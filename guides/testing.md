# Testing Guide

Below are some of our views on writing tests.

This is not exhaustive test guide but it just explore some of the basic things to check when writing tests

In most cases tests have 3 parts:

- tested code(function)
- expectedOutput
- realOutput

`assert(realOutput).toEqual(expectedOutput);

## Redux

### Reducers

case 1: Testing initial state

assertions

- [ ] reducer(undefined,{})
- [ ] reducer(undefined,{type:INVALID})

case 2: Test if it is pure function

assertions

- [ ] reducer(previousState,action) previousState should remain unchanged
- [ ] reducer(previousState,action) action should remain unchanged

```js

it('should be a pure function', () => {
 const previousState = {};
 const action = {type:types.TYPE, data};

 reducer(previousState, action);

 expect(previousState).toEqual(previousState);
 expect(action).toEqual(action);
});
```

case 3: Handle adding items into array

assertions

- [ ] Previous state should be empty array
- [ ] Previous state is not empty array

case 4: Handle changing state field values

- [ ] Test previous state with null fields
- [ ] Test previous state with non null fields

### Actions

Should test action creators for synchronous actions

```js

it('should create an action to reset service request',() => {
 const expectedAction = { type:types.RESET_SERVICE_REQUEST};

 expect(action.resetServiceRequest()).toEqual(expectedAction);
});
```

Should test for dispatched actions for asynchronous actions
