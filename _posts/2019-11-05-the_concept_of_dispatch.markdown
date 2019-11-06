---
layout: post
title:      " The Concept of Dispatch"
date:       2019-11-06 00:08:12 +0000
permalink:  the_concept_of_dispatch
---


![courier picture](https://i.imgur.com/Sq694Vk.jpg)

The word dispatch can be used as both a verb and a noun:

* Dispatch: (verb) to send off or away with promptness or speed.
* Dispatch: (noun) a message sent with speed.

Best coding practices dictate that [functions should be verbs](https://medium.com/coding-skills/clean-code-101-meaningful-names-and-functions-bf450456d90c), so the actual `state.dispatch()` function is referring to the act of sending a message to the Redux store.

I like to imagine that when I call `dispatch()` there is a physical person (a courier if you will) that takes my message (i.e. the action object) and brings it to the Store. Unfortunately, the courier can't bring the message directly to the store because he only accepts state changes that have been vetted by his friends, the reducers. So, the courier goes to each reducer giving them the action message along with the current store state. Each reducer friend takes a look at the action message and returns a new state to the courier. Then finally the courier takes the new state returned from a reducer friend and gives that new state to the Store.

## Using Dispatch

There are [two ways components can dispatch components](https://react-redux.js.org/using-react-redux/connect-mapdispatch).

First, by default, when you use the Redux `connect()` function in your component, you can call `props.dispatch()` within your component. For example:

```
import { Component } from "react";
import { connect } from "react-redux";

export class FooComponent extends Component {
	componentDidMount() {
    	this.props.dispatch({ type: 'SOME_ACTION' });
  	}
}

export default connect()(FooComponent)
```

Second, you can use `mapDispatchToProps()` to make the `dispatch()` function available to your custom action creators. This is especially useful when you need to make async calls. For example:

```
import { Component } from "react";
import { connect } from "react-redux";
import { bindActionCreators } from "redux";

export function doSomething() {
	return function (dispatch) {
		fetch('/onething')
			.then(() => dispatch({ type: 'SOMETHING_ELSE' });
	};
}

export class FooComponent extends Component {
	componentDidMount() {
    	this.props.doSomething();
  	}
}

const mapDispatchToProps = dispatch => {
  return bindActionCreators({ doSomething }, dispatch);
}

export default connect(null, mapDispatchToProps)(FooComponent)
```

## Recap

The key thing to remember about Redux's dispatch functionality is that it facilitates and coordinates between a component that initiates a request to change global state, one or more reducers that translate actions into actual state changes and finally the store itself where the state is maintained.

It is worth re-emphasizing here that all of this rigmarole is necessary and important because of the simple fact that none of your code can change Redux global state directly. Redux state is walled off from anyone touching it other than our good friend, the courier, who has been thoroughly vetted and follows exact procedures and regulations. 



	

