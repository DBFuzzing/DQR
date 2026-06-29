# DQR - Derived Query Relocation

DQR is an extended version of SQLancer with additional database support and enhanced testing capabilities.

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

```bash
# Show general help (lists all databases and options)
java -jar target/sqlancer-2.0.0.jar

# Show help for a specific database
java -jar target/sqlancer-2.0.0.jar mysql
java -jar target/sqlancer-2.0.0.jar postgres
java -jar target/sqlancer-2.0.0.jar duckdb
java -jar target/sqlancer-2.0.0.jar tidb
java -jar target/sqlancer-2.0.0.jar clickhouse
java -jar target/sqlancer-2.0.0.jar mariadb
java -jar target/sqlancer-2.0.0.jar oceanbase
```

### Basic Example

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
