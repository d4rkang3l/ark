# Style Guide
This is the official documentation for the Style Guide we recommend when writing
Alloy code. Note that this is a guide, and not a set of rules; you can write 
your code however you want, but this is what we suggest for keeping it easy to
read, maintain, and write.

This may change, but for now it's pretty solid. Because the language could change
at any point, this will cover a more abstract view of the language and it wont
cover every tiny detail.

## Whitespace
* Use spaces around binary operators:

	fn bar(a: int, b: int): int {
		return a + b;
	}

* Spaces after colons and commas:

	struct Cat { a: int, b: int }

	fn bar(a: Cat);

### Line Wrapping
* Functions with multiple lines in the signatures should have all the parameters
aligned with the first, the return type should be on a separate line, aligned
with the last parameter.

	fn foo(a: int,
		   b: int,
		   c: int
		   ): int {
		...
	}

### Alignment
Code should not use extra whitespace to provide alignment:

	// Good
	int a: int = 5;
	int bar: int = 3;

	// Also good
	struct SomeStruct {
		a: int = 3,
		foo: int = 2
	};

	// Bad
	int a: int   = 5;
	int bar: int = 3;

	// Bad
	struct SomeStruct {
		a: int   = 3,
		foo: int = 2
	};

## Comments
Use line comments:

	// Do some stuff then do some more stuff after that, 
	// close the program after doing stuff.

Instead of:

	/*
	 * Do some stuff then do some more stuff after that, 
	 * close the program after doing stuff.
	 */

## Braces
Braces should be on the same line:

	fn foo(): int {
		...
	}

	fn foo(a: int,
		   b: int,
		   c: int
		   ): int {
		...
	}

	struct Cat {
		...
	}

	impl Cat {
		...
	}

## Naming

	|----------------------------------------------|
	| Item					|	Convention		   |
	|-----------------------|----------------------|
	| Types					|	camelCase		   |
	| Functions 			|	snake_case         |
	| Methods 				|	snake_case         |
	| Local Variables		|	snake_case         |
	| Global Variables		|	snake_case         |
	| Static Variables		|	UPPER_SNAKE_CASE   |
	| Constant Variables	|	UPPER_SNAKE_CASE   |
	|----------------------------------------------|

### Avoid redundant prefixes

#### Good
	struct Cat {
		name: str,
		age: int
	};

	impl Cat {
		fn setName(): void {
			...
		}
	}

##### Bad
	struct Cat {
		catName: str,
		catAge: int
	};

	impl Cat {
		fn setCatName(): void {
			...
		}
	}