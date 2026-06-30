# DQR - Derived Query Relocation

DQR is an extended version of SQLancer with additional database support and enhanced testing capabilities.

## Bug List

This section details the bugs identified by DQR. Each reported issue includes a link to the corresponding bug report or GitHub issue where available.

### MySQL Bugs

*   **[MySQL Bug #119927](https://bugs.mysql.com/bug.php?id=119927)**

*   **[MySQL Bug #119959](https://bugs.mysql.com/bug.php?id=119959)**

*   **[MySQL Bug #120051](https://bugs.mysql.com/bug.php?id=120051)**

*   **[MySQL Bug #120075](https://bugs.mysql.com/bug.php?id=120075)**

*   **[MySQL Bug #120145](https://bugs.mysql.com/bug.php?id=120145)**

*   **[MySQL Bug #119927](https://bugs.mysql.com/bug.php?id=119927)**

### TiDB Bugs
*   **[TiDB Bug #62380](https://github.com/pingcap/tidb/issues/62380)**

*   **[TiDB Bug #62444](https://github.com/pingcap/tidb/issues/62444) Fixed**

*   **[TiDB Bug #62456](https://github.com/pingcap/tidb/issues/62456) Fixed**

*   **[TiDB Bug #62459](https://github.com/pingcap/tidb/issues/62459)**

*   **[TiDB Bug #62460](https://github.com/pingcap/tidb/issues/62460)**

*   **[TiDB Bug #62644](https://github.com/pingcap/tidb/issues/62644) Fixed**

*   **[TiDB Bug #62645](https://github.com/pingcap/tidb/issues/62645) Fixed**

*   **[TiDB Bug #62689](https://github.com/pingcap/tidb/issues/62689)**

*   **[TiDB Bug #63596](https://github.com/pingcap/tidb/issues/63596)**

*   **[TiDB Bug #63601](https://github.com/pingcap/tidb/issues/63601) tlp**

*   **[TiDB Bug #63635](https://github.com/pingcap/tidb/issues/63635)**

*   **[TiDB Bug #63636](https://github.com/pingcap/tidb/issues/63636)**

*   **[TiDB Bug #63736](https://github.com/pingcap/tidb/issues/63736)**

### Percona Bugs
*   **[Percona #10124](https://perconadev.atlassian.net/browse/PS-10124)**

*   **[Percona #10127](https://perconadev.atlassian.net/browse/PS-10127)**

*   **[Percona #535](https://perconadev.atlassian.net/browse/DISTMYSQL-535)**

### DuckDB Bugs
*   **[DuckDB Bug #20483](https://github.com/duckdb/duckdb/issues/20483) Fixed in DuckDB v1.4.3**
  
*   **[DuckDB Bug #20486](https://github.com/duckdb/duckdb/issues/20486) Fixed in DuckDB v1.4.3**

*   **[DuckDB Bug #20608](https://github.com/duckdb/duckdb/issues/20608) Fixed in [Issue #20608: EXCEPT Window Collations](https://github.com/duckdb/duckdb/pull/20645)**

## Quick Start

### Get the Project

```bash
# Clone from GitHub
git clone https://github.com/DBFuzzing/DQR.git
cd DQR

# Or download and extract the gz archive
tar -xzf DQR.tar.gz
cd DQR
```

### Prerequisites

- Java 11 or higher
- Maven 3.6+

### Building

```bash
mvn clean package -DskipTests
```

### Running

After building, run SQLancer with your target database:

**Important**: General options must come **before** the database type, while database-specific options come **after**.

#### Basic Example

```bash
# General options come BEFORE the database type
java -jar target/sqlancer-2.0.0.jar \
    --num-threads 4 \
    --num-tries 100 \
    mysql \
    --host localhost \
    --port 3306 \
    --username test \
    --password test

# For embedded databases like DuckDB (no external server needed)
java -jar target/sqlancer-2.0.0.jar \
    --num-threads 1 \
    --num-tries 10 \
    duckdb
```

## Supported Databases

- MySQL
- PostgreSQL  
- DuckDB
- TiDB
- ClickHouse
- MariaDB
- OceanBase

## Documentation

For detailed usage instructions and advanced options, refer to the official [SQLancer documentation](https://github.com/sqlancer/sqlancer).
