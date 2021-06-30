# extends
 
How use
```js
IMPORT("extends", "__extends");

function ParentClass(){}
ParentClass.prototype.b = 1;

__extends(ChildClass, ParentClass);
function ChildClass(){
    ParentClass.apply(this, arguments);
}
```

# Example

There is a class written in TypeScript

```ts
class ParentClass {
    constructor() {
        alert("Create!");
    }

    public method(a: number | string) {
        alert("method: " + a);
    }
}
```

Inheriting from this class in TypeScript looks like this

```ts

class ChildClass extends ParentClass{
    public method(){
        super.method("Child!");
    }
}
```

How to write this in JavaScript using __extends

```js
IMPORT("extends", "__extends");

function ChildClass(){
    ParentClass.apply(this, arguments);
}
__extends(ChildClass, ParentClass);
ChildClass.prototype.method = function() {
    ParentClass.prototype.method.call(this, "Child!");
}
```