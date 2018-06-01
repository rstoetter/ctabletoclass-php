
# The repository 'rstoetter/ctabletoclass-php'

# Index

## [Description](#index_description)
## [Generated Components](#index_components)
## [Use Cases](#index_use_cases)
## [Provided Classes](#index_classes)
## [Namespaces](#index_namespaces)
## [Installation](#index_installation)
## [Usage Example](#index_example)
## [More Informations](#index_informations)

<a name="index_description"></a><h2>Description</h2>

The PHP class rstoetter\\ctabletoscript\\cTableToClass examines the fields of a table of a SQL database and generates a PHP file, that contains a PHP class, which can be used for common actions (ADD, EDIT, DELETE, DELETE CASCADING) on the table.

<a name="index_components"></a><h2>Generated Components</h2>

The PHP class rstoetter\\ctabletoscript\\cTableToClass examines the fields of a table of a SQL database and generates a PHP file, that contains a PHP class, which can be used for common actions (ADD, EDIT, DELETE, DELETE CASCADING) on the table.

Per table the class generates four class modules :

### common base classes
- a common system base class, which provides a PHP class, which is extended by the common user base class
- a common user base class, which provides a base class, which is extended by all generated table classes. Here you can add your own common code

### table classes
- a system table class, which extends the common user base class and provides all methods necessary to manipulate the data in a table
- a user table class, which extends the system table class and provides all methods you added to manipulate the data in a table

The structure described above makes the code better maintainable as there are system and user code parts. 

- The code generator will overwrite the **system code** (aka 'common system base class' and 'system table class') previously written system code on each run. So you can be sure to benefit from changes later changes of the code generator will bring along in future and that the code base really reflects the actual contents of the table involved.

- The code generator will not touch the **user defined code** (aka the code in the 'common user base class' and 'user table class') once the modules have been generated, when the code generator is executed again and again. Therefore additional code you provided in the special classes will remain in the state you need it for your project.


Let us now act on the assumption, that your database owns three tables 00, 01 and 02. Accordingly the module structure explained above will result in the following class hierarchy:

    cCommonSystemBaseClass
    └── cCommonUserBaseClass
        ├── cSystemTableClass_00
        │   └── cUserTableClass_00
        ├── cSystemTableClass_01
        │   └── cUserTableClass_01
        └── cSystemTableClass_02
            └── cUserTableClass_02

The system classes, which you should not edit, are 

- cCommonSystemBaseClass, 
- cSystemTableClass_00 with code for table '00', 
- cSystemTableClass_01 with code for table '01' and 
- cSystemTableClass_02 with code for table '02'.

The user classes, provided for your convinience, where you can add functionalities you need are 

- the common user cCommonUserBaseClass with code the following classes have in common, 
- the user table class cSystemTableClass_00 with code for table '00', 
- the user table class cSystemTableClass_01 with code for table '01' and 
- the user table class cSystemTableClass_02 with code for table '02'.


<a name="index_use_cases"></a><h2>Use Cases</h2>

<a name="index_classes"></a><h2>Provided Classes</h2>

The class \rstoetter\rstoetter\\ctabletoclass\\\cTableToClass is the main class of the repository rstoetter/ctabletoclass-php.

There are no helper classes necessary in order to use the class cTableToClass:

But you will need PHP 7 or later to use this repository

<a name="index_namespaces"></a><h2>Namespace</h2>

Use the [namespace](http://php.net/manual/en/language.namespaces.php) **rstoetter\rstoetter\\ctabletoclass\\** in order to access the classes provided by the repository rstoetter/ctabletoclass-php.

<a name="index_installation"></a><h2>Installation</h2>

The releases of the repository rstoetter/ctabletoclass-php are hosted by [Packagist](https://packagist.org), the main [composer](https://getcomposer.org/) repository. The repository assumes that you have composer installed. Simply add:

    "require" : {

        "rstoetter/ctabletoclass-php" : ">=1.0.0"

    }

to your **composer.json**, and then you can simply install it with the command:

    composer install

<a name="index_example"></a><h2>Usage Example</h2>

```php

//
// end the program
//

die( PHP_EOL . PHP_EOL . ' program finished in ' . __FILE__ . ' on line ' . __LINE__  . PHP_EOL );


```


<a name="index_informations"></a><h2>More Information</h2>

See the [project wiki of rstoetter/ctabletoclass-php](https://github.com/rstoetter/ctabletoclass-php/wiki) for more technical informations.

