# CSharp member matching
Here is listed all possible member matching. All of them can use partial or fully qualified name, in case of multiple matching Projbook will aggregate all matching members. The member matching never consider memeber type and will apply on any member simply based on the name.
The member matching follows this syntax `csharp[<fileName>] <optionalOption><member>`.
* `<fileName>`: Any file name in the current documentation project, it's possible to reach code content outside of the document project by adding a project reference from the documentation project to another solution's project.
* `<optionalOption>`: Options member, see [options](#page%2freference.md-options).
* `<member>`: The member to extract, see the following section for details on all supported member matching

## Namespaces
* `csharp[File.cs] MyNamespace`: Match the namespace `MyNameSpace`
* `csharp[File.cs] My.Namespace`: Match the namespace `My.NameSpace` or the sub namespace `Namespace` of `My` namespace

## Classes
* `csharp[File.cs] ClassName`: Match any class nammed `ClassName`
* `csharp[File.cs] ClassName.SubClassName`: Match any class nammed `SubClassName` located inside `ClassName`

## Methods
* `csharp[File.cs] ClassName.MethodName`: Match any method nammed `MethodName` of the class `ClassName`
* `csharp[File.cs] MethodName`: Match any method nammed `MethodName`
* `csharp[File.cs] MethodName(string, int)`: Match any method nammed `MethodName` with two parameters of type string and int
* `csharp[File.cs] (string, int)`: Match any method with two parameters of type string and int

## Properties
* `csharp[File.cs] ClassName.PropertyName`: Match any property nammed `PropertyName` of the class `ClassName`
* `csharp[File.cs] Property`: Match any property nammed `PropertyName`
* `csharp[File.cs] Property.get`: Match the getter of any property nammed `PropertyName`
* `csharp[File.cs] get`: Match any getter

## Indexers
* `csharp[File.cs] ClassName.[int]`: Match any indexer using the type `int` of the class `ClassName`
* `csharp[File.cs] [int]`: Match any indexer using the type `int`

## Events
* `csharp[File.cs] ClassName.EventName`: Match any event nammed `EventName` of the class `ClassName`
* `csharp[File.cs] EventName`: Match any property nammed `EventName`
* `csharp[File.cs] EventName.add`: Match the adder of any event nammed `EventName`
* `csharp[File.cs] add`: Match any adder

## Constructors
* `csharp[File.cs] ClassName.<Constructor>`: Match any constructor of the class `ClassName`
* `csharp[File.cs] <Constructor>`: Match any constructor
* `csharp[File.cs] <Constructor>(string, int)`: Match any constructor with two parameters of type string and int

## Destructors
* `csharp[File.cs] ClassName.<Destructor>`: Match any destructor of the class `ClassName`
* `csharp[File.cs] <Destructor>`: Match any destructor

## Generics
* `csharp[File.cs] ClassName{T}`: Match any class nammed `ClassName` with a type parameter `T`
* `csharp[File.cs] ClassName{T, U}`: Match any class nammed `ClassName` with two type parameter `T` and `U`
* `csharp[File.cs] ClassName.MethodName{T}`: Match any method nammed `MethodName` of the class `ClassName` with a type parameter `T`
* `csharp[File.cs] ClassName.MethodName{T}(T)`: Match any method nammed `MethodName` of the class `ClassName` with a type parameter `T` having a parameter of type `T`
* `csharp[File.cs] ClassName{T}.MethodName{U}(U)`: Match any method nammed `MethodName` of the class `ClassName` having a type parater `T` with a type parameter `U` having a parameter of type `U`

## Options
* `=`: Code structure only including the member with all motifier, documentation and signature but replace the code block content by `// ...`
* `-`: Code content only, it will remove the code structure and will produce what's located inside the code block only

# Xml member matching
CSharp matching simply follow Projbook's syntax for member matching but use XPath as member selector.
The member matching follows this syntax `csharp[<fileName>] <xpath>`.
* `<fileName>`: Any file name in the current documentation project, it's possible to reach code content outside of the document project by adding a project reference from the documentation project to another solution's project.
* `<xpath>`: The XPath query performing the member selection, see [XPath reference](https://msdn.microsoft.com/en-us/library/ms256115)

# Source example
Have a look to this documentation pages as example [source](https://github.com/defrancea/Projbook/tree/master/src/Projbook.Documentation/Page)