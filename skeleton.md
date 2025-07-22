# blurb
In the Coding and Analysis Techniques learning group, we will explore how Polars can be leveraged for efficient data processing: Ben will cover its key features and improvements over Pandas, and demonstrate practical applications with parquet and NWB files.

# skeleton
# $ = call out design philosopy
1. Apache Arrow:
    - key features and benefits
        numpy has: int64, float64, string, datetime
        - full support for complex data types (nulls, strings, datetime, nested structures)
        - lower memory footprint
        - efficient interchange between different languages/libraries
    - used by: polars, pandas 2.0/3.0
    - parquet
        - schema
        - compressed
        - columnar
        - predicate pushdown

2. Polars
    # present concepts, then code snippets
    - who made it, why, inspirations
        - Ritchie Vink
        - data engineering
        - SQL
        - 10-things blogpost
    - key features and benefits
        - Rust-based, high-performance dataframe library
            - parallelized operations by default - use all available CPU cores
            - memory-efficient operations
        - lazy evaluation for optimized query execution
            - projection and predicate pushdown $(only load required data)
            - also allows processing of larger-than-memory datasets
    - comparison with pandas
        - show repr
        - API improvements
            - no index $(row content-based filterin, like `pd.query`)
            - consistency (names, parameters, chain-ability etc. Carefully planned)
            - chaining (more concise code)
            - $(generally no inplace operations)
            - fully-typed (helps when making long chains )
        - performance benchmarks
    - expressions
    - key methods
        - filter, with_columns, groupby, join, select
    - polars <> pandas
    - parquet <> polars
        - folders of parquet files as single dataframe
    - polars <> altair $(long-format data)

3. Demos
    - read parquet
    - basic filtering
    - groupby operations
    - scan parquet -> lazyframe
        - query plan graph
    - lazyframe from NWB files
    - plotting with altair