- Angular compiler starts from main.ts which has bootstrapped the root module
- Only in root module we require to bootstrap the component nowehere else
- we can bootstrap multiple components and use them in index.html
	- ![[Pasted image 20220904123245.png]]
	- ![[Pasted image 20220904123259.png]]
- You can create custome events using eventEmitter