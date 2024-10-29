
# Laravel Coding Conventions and Best Practices

This document details the best practices and coding conventions for our Laravel project using PHP 8.3 and Laravel 11. Adhering to these conventions will help maintain clean code and scalable architecture, especially as the codebase grows.

## PHP Standards Recommendations (PSR)

Code **MUST** follow all rules outlined in **PSR-1**.

---

### Namespace and Class Names

Class names **MUST** be declared in **StudlyCaps**.

```php
<?php

namespace Vendor\Model;

class Foo
{
    // Class body
}
```

### Class Extending & Interface Implements

Example of a class extending another and implementing an interface:

```php
<?php

namespace Vendor\Package;

use FooInterface;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class Foo extends Bar implements FooInterface
{
    public function sampleMethod($a, $b = null)
    {
        if ($a === $b) {
            bar();
        } elseif ($a > $b) {
            $foo->bar($arg1);
        } else {
            BazClass::bar($arg2, $arg3);
        }
    }

    final public static function bar()
    {
        // Method body
    }
}
```

### Constants

Class constants **MUST** be in uppercase with underscore separators:

```php
<?php

namespace Vendor\Model;

class Foo
{
    const VERSION = '1.0';
    const DATE_APPROVED = '2012-06-01';
}
```

---

## Naming Conventions

### Method Names

- Method names **MUST** use **lowerCamelCase**.
- Only `a-z`, `A-Z`, and `0-9` characters are allowed.
- Avoid underscores and special characters.
- Constructors **MUST** always be named `__construct()`.

Correct Naming Conventions:
- `myMethod()`
- `betterWriteLongMethodNamesThanNamesNobodyUnderstands()`

Incorrect Naming Conventions:
- `my_method()`
- `some_nice_method_name()`

### Variable Names

Variable names **MUST** use **lowerCamelCase** and be self-explanatory.

Correct Naming Examples:
- `$singletonObjectsRegistry`
- `$argumentsArray`

Incorrect Naming Examples:
- `$singleton_objects_registry`
- `$arguments_array`

---

## PHP Code Formatting

### PSR-2 Standards

We follow the **PSR-2** standard for PHP code formatting. You can read the full [PSR-2 standard here](https://www.php-fig.org/psr/psr-2/).

### Strings

- **Single Quotes** for literal strings:
    ```php
    $project = 'A great project';
    ```
- **Concatenation** with spaces around the dot:
    ```php
    $message = 'Hey ' . $name . ', you look ' . $appearance . ' today!';
    ```
- **Multi-Line Strings** with dot operator:
    ```php
    $project = 'A great ' . 'project from ' . 'a great ' . 'team';
    ```

Consider `sprintf()` for readability:
```php
$message = sprintf('Hey %s, you look %s today!', $name, $appearance);
```

---

## Documentation

### Class Documentation

Add a documentation block describing each class's purpose.

```php
/**
 * Short description of the class.
 *
 * Detailed description about the class’s functionality.
 */
class SomeClass
{
    // Class body
}
```

### Variables, Constants, and Includes

Document properties of a class briefly:

```php
/**
 * A short description of the property
 *
 * @var string
 */
protected $title = 'Untitled';
```

### Method Documentation

Document parameters and return values if they add clarity.

```php
/**
 * Description of the method.
 *
 * @param Post $post Description of $post
 * @param string $someString Description of $someString
 */
public function addStringToPost(Post $post, string $someString): void
{
    // Method body
}
```

---

## Control Structures

### If-Else Statements

**if** structures follow this format:

```php
<?php

if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body
}
```

Use **elseif** instead of **else if** for single-word control keywords.

### Switch Cases

**Switch** structures follow this format:

```php
<?php

switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
        echo 'Third case';
        return;
    default:
        echo 'Default case';
        break;
}
```

---

## Testing Documentation

Test cases should be marked as tests and include appropriate annotations.

```php
/**
 * @test
 */
public function fooReturnsBarForQuux(): void
{
    // Test body
}
```

---

## Modularity

We are using the **Laravel modular structure**. Always define or create components within their relevant module. Follow the **SOLID principles** and maintain strict separation between modules to ensure maintainable code.

---

By following these guidelines, we can maintain a clean, readable, and scalable codebase throughout the project.
