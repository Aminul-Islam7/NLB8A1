# TypeScript Access Modifiers
Access Modifiers are some reserved keywords in TypeScirpt (and many other programming languages) that are used to control the visibility and accessibility of Classes. These are part of the concept of Encapsulation in OOP (Object Oriented Programming). Encapsulation is one of the four fundamental principles of OOP which bundles data into a single unit (capsule) called Class, and protects it's internal state from unwanted tampering and enforces controlled modification for its members.

There are three Access Modifiers in TypeScript:
- `public` - It is accessible from anywhere inside or outside the Class. All members are 'public' by default.
- `private` - It is only accessible inside the Class. It can't be accessed from any other Class, or anywhere outside the Class.
- `protected` - It can only be accessed inside the Class and from its Subclasses (the Classes that inherit from it.)

```ts
class Employee {
	public name: string; // accessible everywhere
	protected id: number // accesible within this class and subclasses
	private salary: number // accessible only within this class
	
	constructor(name: string, id: number, salary: number) {
		this.name = name;
		this.id = id;
		this.salary = salary;
	}
}
```

However, private or protected members' access can also be modified/controlled further using getter or setter methods.

A related keyword is `readonly`, which is a property modifier that controls the mutability but not the visibility. Applying `readonly` to a property makes it immutable from everywhere. And it can be combined with the access modifiers.

```ts
class Employee {
	public readonly name: string; // visible everywhere but value can't be updated once initialized
	...
}
```

In conclusion, Access Modifiers are tools to protect the states of Class members from unwanted changes that were not intended in the original design of the Class.