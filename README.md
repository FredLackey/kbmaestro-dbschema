# kbmaestro-dbschema
Macro library for the rapid creation of database entity relationship diagram (ERD) within DbSchema.

## Dependencies  
You must have both of the following tools installed to make use of this project:

[Keyboard Maestro](https://www.keyboardmaestro.com) Macro Engine for macOS / OS X  
[DbSchema](https://www.dbschema.com/) Cross-Platform Diagram Designer and Query Tool   

## Why DbSchema?  
I've developed software professionally now for over three decades and, during that time, I have grown to value tools which are both reliable and platform independent.  DbSchema is both.  Since I work with a large number of global clients, I cannot predict what OS or database I will be using tomorrow.  DbSchema has worked flawlessly on all three platforms (Windows, Mac, and Linux) as well as every single database I have thrown at it (MySql, Postgres, SQL Server, MariaDb, etc.).  Additionally, unlike crap-ware, like Toad and MySql Workbench, DbSchema offers a polished and virtually flawless experience every time.

## Postgres vs MySql  
As of the last release, Postgres is my relational database of choice.  The Postgres library is newly created and will be the focus of these macros moving forward.  It is recommended that you focus on Postgres to ensure your library is as accurate and current as possible.

## Installation
Once Keyboard Maestro is installed, simply browse to the library file and double-click the library you wish to use.  The library files are located in...  

[./files/DbSchema - MySql Macros.kmlibrary](https://raw.githubusercontent.com/FredLackey/kbmaestro-dbschema/master/files/DbSchema%20-%20MySql%20Macros.kmlibrary)  (for MySql)  
[./files/DbSchema - MySql Macros.kmlibrary](https://raw.githubusercontent.com/FredLackey/kbmaestro-dbschema/master/files/DbSchema%20-%20Postgres%20Macros.kmlibrary)  (for Postgres)

## Usage
This library allows for rapidly creating new tables, indexes, and foreign keys within a single DbSchema layout.  Currently, there are **over 100 commands** for rapidly creating columns, indexes, and foreign keys in your tables:  

![Keyboard Maestro](https://github.com/FredLackey/kbmaestro-dbschema/raw/master/docs/img/kbmaestro.png)

There isn't an actual "command line" in DbSchema, so the macros use the descritpion field of the "New Table" (or "Edit Table") dialog to kick things off.  Just type the needed command:

![DbSchema Commands](https://github.com/FredLackey/kbmaestro-dbschema/raw/master/docs/img/kbmaestro_commands.png)

## Command Syntax
Each command is split up in 1-3 parts.  For example, to create a field with a specific data type and length, the command is:

`<DATA TYPE ABBREVIATION><LENGTH><NULLABLE FLAG><SPACE>`

So, to create a `varchar(255)` column, you would type either `vc255` or `vc255n` (for nullable)

***Remember, a single space must follow your command to show it is complete.***

## Available Commands

### Simple Field Types  
You will be prompted for a field name unless otherwise specified:  

* `idNNN` : `char(NNN) PRIMARY KEY` (name of field is `id`, valid lengths: 1, 2, 3, 32)
* `pidNNN` or `pidNNNn` : `char(NNN)` (valid lengths: 1, 2, 3, 32)

### Primative Field Types  
You will be prompted for a field name:  

* `b` or `bn` : `boolean`
* `cNNN` or `cNNNn` : `char(NNN)` (valid lengths: 1, 2, 3, 5, 10, 20, 30, 50, 100, 255)
* `d` or `dn` : `datetime`
* `f` or `fn` : `float`
* `i` or `in` : `integer`
* `vcNNN` or `vcNNNn` : `varchar(NNN)` (valid lengths: 1, 2, 3, 5, 10, 20, 30, 50, 100, 255)

### Function Commands
Perform multi-step actions.  

* `fk` : Create foreign key on current table.  Prompts for local field name and primary table name.
* `ffk` : Same as above, however prompts for schema name of primary table.
* `idx` : Create single or multi-column index on current table.  Prompts for field name(s).
* `uidx` : Create single or multi-column **unique** index on current table.  Prompts for field name(s).

### Audit Trail

* `_d` : Create `datetime null` field as delete flag.  
* `_m` : Create `char(32) not null` field as member id (MySql only).  
* `_u` : Create `bigint not null` field as user id (Postgres only).  
* `_v` : Create `datetime not null` field as version date.  
* `_audit` : Triggers all three audit trail macros for convenience.  

### Convenience

* `desc` : `varchar(255) NULL` named `desc`
* `description` : `varchar(255) NULL` named `description` (prevents keyword conflicts)
* `ename` : `varchar(50) NOT NULL` named `enum_name`
* `name` : `varchar(50) NOT NULL` named `name`
* `lname` : `varchar(100) NOT NULL` named `name`
* `tid` : `char(2) NOT NULL` named `type_id`

## Important Requirement
**Depending on the library used, your DbSchema diagram must be set to MySql or Postgres as the target database.**  This was chosen to standardize on a single "starting point" for all diagrams.  However, **you may change database platforms once your diagram is complete**.

#### Why MySql?  
DbSchema allows for easily switching from one database to another.  For example, if your project is designed in Database X (SQL Server, for example), you may easily switch it to Database Y (Postgres, MySql, MariaDb, etc.) by simply clicking your mouse.  DbSchema gracefully translates all of the datatypes, fields, and other assets.  MySql was chosen since it is widely used on all major operating systems.

-----

## Author

Fred Lackey  
[fred.lackey@gmail.com](mailto:fredlackey@gmail.com)  
[www.fredlackey.com](http://www.fredlackey.com)  