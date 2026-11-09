# TypeScript Interface Vs Type Alias: When to Use Which One

Type aliases and Interfaces are ways to define custom types in TypeScript. These help us create the structure for our variables, making it easier to code using intellisense suggestions and spot bugs during development or compilation.

According to official TypeScript documentation, we should be using interface by default, and use type alias only when it's strictly required or an interface cannot serve the need.

Type alias examples:

```ts
type Age = number; // Renaming primitive type
type Sunday = 'sunday'; // Literal type
type Id = string | number; // Primitive type union
type Role = 'admin' | 'member'; // String literal union
```

Interfaces can be extended directly:

```ts
interface Animal {
	species: string;
}

interface Cat extends Animal {
	breed: string;
}

const c: Cat = { species: 'Felis catus', breed: 'Persian' };
```

Type alias can be extended by merging using intersection operator:

```ts
type Vehicle = {
	brand: string;
};

type Car = Vehicle & {
	model: string;
};

const c: Car = { brand: 'Toyota', model: 'Corolla' };
```

If an interface is redefined with the same name, TypeScript merges the properties into a single interface.

```ts
interface User {
	name: string;
}

interface User {
	age: number;
}

// Resulting interface 'User' has both 'name' and 'age':
const user: User = { name: 'Aminul', age: 24 };
```

But a type alias cannot be redefined with the same name again, it throws a compilation error.

So in general, we use interface for object types and type alias for primitives, tuples, literals, type unions/intersections, etc.
