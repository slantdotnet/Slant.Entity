Slant library for Entity Framework
==============

## Overview

There are two namespaces which contain ready-to-use classes.

####Slant.Linq 

It is a free set of extensions for LINQ and Entity Framework power users. It comprises the following:

* An extensible implementation of AsExpandable()
* A public expression visitor base class (ExpressionVisitor)
* PredicateBuilder
* Linq.Expr and Linq.Func shortcut methods

With Slant.Linq, you can:

* Plug expressions into EntitySets and EntityCollections
* Use expression variables in subqueries
* Combine expressions (have one expression call another)
* Dynamically build predicates
* Leverage AsExpandable to add your own extensions.

####Slant.Entity

It provides simple and flexible way to manage your Entity Framework DbContext instances.

`DbContextScope` was created out of the need for a better way to manage DbContext instances in Entity Framework-based applications. 

The commonly advocated method of injecting DbContext instances works fine for single-threaded web applications where each web request implements exactly one business transaction. But it breaks down quite badly when console apps, Windows Services, parallelism and requests that need to implement multiple independent business transactions make their appearance.

The alternative of manually instantiating DbContext instances and manually passing them around as method parameters is (speaking from experience) more than cumbersome. 

`DbContextScope` implements the ambient context pattern for DbContext instances. 

It's something that NHibernate users or anyone who has used the `TransactionScope` class to manage ambient database transactions will be familiar with.

It doesn't force any particular design pattern or application architecture to be used. It works beautifully with dependency injection. 

And it works beautifully without. It of course works perfectly with async execution flows, including with the new async / await support introduced in .NET 4.5 and EF6. 

And most importantly, at the time of writing, `DbContextScope` has been battle-tested in a large-scale applications for a long time. 

## Installation

We recommended installing [the NuGet package](https://www.nuget.org/packages/NSpectator). Install on the command line from your solution directory or use the Package Manager console in Visual Studio:

```powershell

PM> Install-Package NSpectator

```

## Usage

Check out our wiki to see typical and non-trivial usages and detailed examples:

[Using LINQ Extensions](https://github.com/slantdotnet/Slant.Entity/wiki/Using-LINQ-Extensions)

[Using DbContextScope](https://github.com/slantdotnet/Slant.Entity/wiki/Using-DbContextScope)

## Contributing

Check out [this wiki page](https://github.com/slantdotnet/Slant.Entity/wiki/Contributing) for complete guide.

## Thanks to

Jetbrains Community Support for providing great tools for our team

[![Jetbrains Resharper](http://nspectator.org/assets/icon_ReSharper.png)](https://www.jetbrains.com/resharper/)


