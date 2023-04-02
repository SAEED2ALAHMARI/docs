[View code on GitHub](https://dune.com/docs/query/DuneSQL-reference/Functions-and-operators/table.md)

# Table Functions

This technical guide explains table functions in the DuneSQL project. A table function is a function that returns a table and can be invoked inside the `FROM` clause of a query. The row type of the returned table can depend on the arguments passed with invocation of the function. If different row types can be returned, the function is a **polymorphic table function**. Polymorphic table functions allow you to dynamically invoke custom logic from within the SQL query. They can be used for working with external systems as well as for enhancing Trino with capabilities going beyond the SQL standard.

The guide explains how to invoke a table function in the `FROM` clause of a query. Table function invocation syntax is similar to a scalar function call. Every table function is provided by a catalog, and it belongs to a schema in the catalog. You can qualify the function name with a schema name, or with catalog and schema names. Otherwise, the standard Trino name resolution is applied. The connection between the function and the catalog must be identified because the function is executed by the corresponding connector. If the function is not registered by the specified catalog, the query fails.

The guide also explains two conventions of passing arguments to a table function: arguments passed by name and arguments passed positionally. In the first convention, you can pass the arguments in arbitrary order. Arguments declared with default values can be skipped. Argument names are resolved case-sensitive, and with automatic uppercasing of unquoted names. In the second convention, you must follow the order in which the arguments are declared. You can skip a suffix of the argument list, provided that all the skipped arguments are declared with default values. You cannot mix the argument conventions in one invocation.

The guide also explains that all arguments must be constant expressions, and they can be of any SQL type, which is compatible with the declared argument type. You can also use parameters in arguments. The guide provides examples of how to use table functions in SQL queries.

However, the guide also warns that table functions are currently not in operation in DuneSQL and are a placeholder for future work. The guide also provides links to the developer guide and connector documentation for more information about adding new table functions and supported table functions, respectively.
## Questions: 
 1. What is the purpose of a table function in DuneSQL?
- A table function is a function returning a table that can be invoked inside the `FROM` clause of a query. It allows for dynamically invoking custom logic from within the SQL query, and can be used for working with external systems as well as for enhancing Trino with capabilities going beyond the SQL standard.

2. How are table functions declared and supported in DuneSQL?
- Connectors declare support for different functions on a per-connector basis through implementing dedicated interfaces. For guidance on adding new table functions, see the developer guide. For more information about supported table functions, refer to the connector documentation.

3. What are the conventions for passing arguments to a table function in DuneSQL?
- There are two conventions for passing arguments to a table function: arguments passed by name and arguments passed positionally. All arguments must be constant expressions and can be of any SQL type compatible with the declared argument type. Parameters can also be used in arguments. Mixing the argument conventions in one invocation is not allowed.