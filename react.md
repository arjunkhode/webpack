React.js

Unidirectional data

Blow away - refresh everything
But DOM is expensive
If you wanna type and change another component at the same time, you can't just dump everything out.
Lose their state
Anything changes, just start over 
Do it good. Performant. React.
A javascript library for building UI.
View.

Declarative components
Describe what your component looks like at any point in time.
More than a template
Components are reusable API encompassing - HTML, CSS, JS.
No explicit data binding.

1.How are things rendered?
2.How do updates happen

- Initial render
one render function.
returns a representation of your view.
Recursively call render. Generates a huge string.
Inject it in the document.
2-pass rendering:
	- generate markup
	- attach events
Can run server side or client side
generates a string.
Injects it.
Attaches events to it ASA JS is ready

How it works
	- Render function. Generate a representation
	- Render again. Generate again.
	- Compare them. Find all the differences.
	- Generate mutations in a minimal set, and push them onto the view.

__

Flicker in input when max length is reached:
	- The system knows at a higher level in the hierarchy that the new length is invalid. So the input responds to the event only after it has been computed by the JS, so the input never flickers.
	- This is just like how a mobile operates. When you touch, the kernel handles it first, then figures out the co-ordinates, then the application that was open and then handle the event.
	- Everything in React is synthetic. The events are fake, the DOM is fake.
	- One small read, a lot many writes. Performs well in the DOM.
	- Checks the minimal set of mutations possible.
	- Wouldn't the size of the virtual DOM be large? Not really, JS objects are small. It is the render that takes the space, which is called only after the minimal set is computer.
	- They capture bubble events and form the structure of the synthetic DOM.
	- React is completely detached from the DOM. Has a React root. Has a tree.
