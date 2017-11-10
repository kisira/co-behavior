# co-behavior
A Polymer behavior, implementing the [co](https://github.com/tj/co) generator in Polymer.  [co](https://github.com/tj/co) is implmented as a behavior. A simple way to use it is as part of a a polymer function as below:

```js
<link rel="import" href="co-behavior.html">
....

class SomeClass extends Polymer.mixinBehaviors(
            [                                                                
                Polymer.CoBehavior
            ], Polymer.Element) {

_fetchStuff() {
    var self = this;
    return new Promise(function(resolve, reject) {
        .....
        resolve(stuff);

    });
}

__fetchSomething() {
    let something = function*() {
        let stuff = yield this.__fetchStuff.call(this);            
        this.someProperty = stuff;            
    };
    return this.co(something.call(this));
}

```
Read more about [co](https://github.com/tj/co) and generators [here](http://tobyho.com/2015/12/27/promise-based-coroutines-nodejs/) 
