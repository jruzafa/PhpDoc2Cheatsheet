PhpDoc2Cheatsheet
=================

https://phpdoc2cheatsheet.joseruzafa.com

[File](#file)
[Variable](#variable)
[Class](#class)
[Function](#function)
[Tags](#tags)
[Arrays](#arrays)
[Multiple Types](#multiple_types)

File
====

```php
/** File docBlock description
 *
 * This block demonstrates the rich
 * information that can be included
 * in in-code documentation through
 * DocBlocks and tags
 * @author Jane Doe 
 * @version 1.0
 * @package sample
 */
```

Variable
========

```php
/**
 * Global variable declaration docBlock
 * @global integer $GLOBALS['_myvar']
 * @name $_myvar
 */
$GLOBALS['_myvar'] = 6;
```

Class
=====

```php
/**
 * An example class, this is grouped with
 * other classes in the "sample" package and
 * is part of "classes" subpackage
 * @package sample
 * @subpackage classes
 */
class myclass
{
	...
}
```

Function
========

```php
/**
 * A sample function docblock
 * @global string document the use $_myvar
 * @staticvar integer $staticvar is returned
 * @param string $param1 name to declare
 * @param string $param2 value of the name
 * @return integer
 */
function aFunc($param1, $param2 = 'optional')
{
	static $staticvar = 7;
	global $_myvar;
	return $staticvar;
}
```

Tags
====

@api

```php
/**
 * This method will not change until a major release.
 *
 * @api
 *
 * @return void
 */
function showVersion()
{
	...
}
```

@author

```php
/**
 * @author My Name
 * @author My Name 
 */
```

@category

```php
/**
 * Page-Level DocBlock
 *
 * @category MyCategory
 * @package  MyPackage
 */
```

@copyright

```php
/**
 * @copyright 1997-2005 The PHP Group
 */
```

@deprecated

```php
/**
 * @deprecated
 * @deprecated 1.0.0
 * @deprecated No longer used by internal code and not recommended.
 * @deprecated 1.0.0 No longer used by internal code and not recommended.
 */
function count()
{
	...
}
```

@example

```php
/**
 * @example example1.php Counting in action.
 * @example http://example.com/example2.phps Counting in action by a 3rd party.
 * @example "My Own Example.php" My counting.
 */
function count()
{
	...
}
```

@filesource

```php
/**
 * @filesource
 */
```

@global

This tag is not included in phpDocumentor 2.0

```php
/**
 *@global [Type] [name] @global [Type] [description]
 */
```

@ignore

```php
if($ostest)
{
	/**
	 * This define will either be 'Unix' or 'Windows'
	 */
	define("OS","Unix");
}
else
{
	/**
	 * @ignore
	 */
	define("OS","Windows");
}
```

@internal

```php
/**
 * @internal
 *
 * @return integer Indicates the number of items.
 */
function count()
{
	...
}
```

@link

Normal tag:

```php
/**
 * @link http://example.com/my/bar Documentation of Foo.
 *
 * @return integer Indicates the number of items.
 */
function count()
{
	...
}
```

Inline tag:

```php
/**
 * This method counts the occurrences of Foo.
 *
 * When no more Foo ({@link http://example.com/my/bar}) are given this
 * function will add one as there must always be one Foo.
 *
 * @return integer Indicates the number of items.
 */
function count()
{
	...
}
```

@license

```php
/**
 * @license GPL
 * @license http://opensource.org/licenses/gpl-license.php GNU Public License
 */
```

@method

```php
class Parent
{
	public function __call()
	{
		...
	}
}

/**
 * @method string getString()
 * @method void setInteger(integer $integer)
 * @method setString(integer $integer)
 */
class Child extends Parent
{
	...
}
```

@package

```php
/**
 * @package PSR\Documentation\API
 */
```

@param

```php
/**
 * Counts the number of items in the provided array.
 *
 * @param mixed[] $array Array structure to count the elements of.
 *
 * @return int Returns the number of elements.
 */
function count(array $items)
{
	...
}
```

@property

```php
class Parent
{
	public function __get()
	{
		...
	}
}

/**
 * @property string $myProperty
 */
class Child extends Parent
{
	...
}
```

@property-read

```php
class Parent
{
	public function __get()
	{
		...
	}
}

/**
 * @property-read string $myProperty
 */
class Child extends Parent
{
	...
}
```

@property-write

```php
class Parent
{
	public function __set()
	{
		...
	}
}

/**
 * @property-write string $myProperty
 */
class Child extends Parent
{
	...
}
```

@return (Singular type)

```php
/**
 * @return integer Indicates the number of items.
 */
function count()
{
	...
}
```

@return (two types)

```php
/**
 * @return string|null The label's text or null if none provided.
 */
function getLabel()
{
	...
}
```

@see

```php
/**
 * @see http://example.com/my/bar Documentation of Foo.
 * @see MyClass::$items           for the property whose items are counted
 * @see MyClass::setItems()       to set the items for this collection.
 *
 * @return integer Indicates the number of items.
 */
function count()
{
	...
}
```

@since

```php
/**
 * @since 1.0.1 First time this was introduced.
 *
 * @return integer Indicates the number of items.
 */
function count()
{
	...
}

/**
 * @since 1.0.2 Added the $b argument.
 * @since 1.0.1 Added the $a argument.
 * @since 1.0.0
 *
 * @return void
 */
function dump($a, $b)
{
	...
}
```

@source

```php
/**
 * @source 2 1 Check that ensures lazy counting.
 */
function count()
{
	if(null === $this->count)
	{
		...
	}
}
```

@subpackage

```php
/**
 * @package PSR
 * @subpackage Documentation\API
 */
```

@throws

```php
/**
 * Counts the number of items in the provided array.
 *
 * @param mixed[] $array Array structure to count the elements of.
 *
 * @throws InvalidArgumentException if the provided argument is not of type
 *     'array'.
 *
 * @return int Returns the number of elements.
 */
function count($items)
{
	...
}
```

@todo

```php
/**
 * Counts the number of items in the provided array.
 *
 * @todo add an array parameter to count
 *
 * @return int Returns the number of elements.
 */
function count()
{
	...
}
```

@uses & @used-by

```php
/**
 * @uses MyClass::$items to retrieve the count from.
 *
 * @return integer Indicates the number of items.
 */
function count()
{
	...
}
```

@version

```php
/**
 * @version 1.0.1
 */
class Counter
{
	...
}

/**
 * @version GIT: $Id$ In development. Very unstable.
 */
class NeoCounter
{
	...
}
```

Arrays
======

unspecified:

```php
/*
 * @return array
 */
```

specified containing a single type:

```php
/*
 * @return int[]
 */
```

specified containing multiple types:

```php
/*
 * @return (int|string)[]
 */
```

Multiple Types
==============

```php
/*
 * @return int|null 
 */
```
