# Dart Variables and Null Safety

## Creating and Initializing Variables

In Dart, you can create and initialize variables in different ways:

Using var: Automatically infers the type.

<pre>
  <code>
    var name = "Bob";
  </code>
</pre>

Using explicit types: Specify the type directly.

<pre>
  <code>
    String name = "Bob";
    Object name = "Bob"; // If type can vary
  </code>
</pre>

# Null Safety

Dart enforces sound null safety, preventing runtime errors caused by accessing null values. Here's how it works:

# Nullable vs Non-nullable

<b>Nullable:</b> Can be null or a value.

<pre>
  <code>
    String? name; // Can be null or a string
  </code>
</pre>

<b>Non-nullable:</b> Must have a value.

<pre>
  <code>
    String name; // must have a value
  </code>
</pre>

# Late Variables

<b>late Modifier:</b> Used for variables that will be initialized later or are lazily initialized.

<pre>
  <code>
late String description;

void main() {
  description = 'Feijoada!';
  print(description);  // description is initialized before use
}

  </code>
</pre>

<b>Lazy Initialization:</b> Initialization happens the first time the variable is used.

<pre>
  <code>
    late String temperature = readthermemoter(); // Called only when temperature is used.
  </code>
</pre>

Final and Const

final: Can be set only once.

<pre>
  <code>
final name = 'Bob';
final String nickname = 'Bobby';

  </code>
</pre>

const: Compile-time constant, implicitly final.

<pre>
  <code>
const bar = 1000000;
const double atm = 1.01325 * bar;

  </code>
</pre>

Const for Values and Constructors:

<pre>
  <code>
var foo = const [];
final bar = const [];
const baz = [];  // Equivalent to `const []`

  </code>
</pre>

Type Checks and Collections with const:

<pre>
  <code>
const Object i = 3;
const list = [i as int];  // Typecast
const map = {if (i is int) i: 'int'};  // Collection if
const set = {if (list is List<int>) ...list};  // Spread operator

  </code>
</pre>

## Mutability:

Final objects cannot be reassigned, but their fields can change.

Const objects and their fields are immutable.

By following these guidelines, Dart ensures safer code with fewer runtime errors.



