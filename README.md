# endlab-2200032657
# Hibernate Criteria Query Language (HCQL) Example

This is a Maven-based Hibernate project that demonstrates the usage of Hibernate Criteria Query Language (HCQL) to perform various database operations on a `Customer` entity.

## Features
- **Entity Definition**: The `Customer` entity includes the following fields:
  - `ID` (Auto-generated)
  - `Name`
  - `Email`
  - `Age`
  - `Location`

- **Operations**:
  - Insert records manually using Hibernate.
  - Apply restrictions using Hibernate Criteria API, such as:
    - `equal`
    - `not equal`
    - `less than`
    - `greater than`
    - `between`
    - `like`

## Technologies Used
- Java
- Hibernate (Core)
- MySQL (Database)
- Maven (Build Tool)

## Project Structure

├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── klef
│   │   │           └── jfsd
│   │   │               ├── exam
│   │   │               │   ├── Customer.java
│   │   │               │   └── ClientDemo.java
│   │   └── resources
│   │       └── hibernate.cfg.xml
├── pom.xml


## Setup Instructions
1. **Clone the Repository**
   bash
   git clone https://github.com/<your-username>/hibernate-criteria-example.git
   cd hibernate-criteria-example
   

2. **Configure the Database**
   - Ensure MySQL is installed and running.
   - Create a database (e.g., `hibernate_example`).
   - Update `hibernate.cfg.xml` with your database credentials.

3. **Build the Project**
   bash
   mvn clean install
   

4. **Run the Application**
   - Execute the `main` method in `ClientDemo` to insert records and apply criteria queries.

5. **Inspect the Database**
    Check the `customers` table for the inserted records and query results.

## Example Queries
### Insert Records
java
Customer customer1 = new Customer();
customer1.setName("John Doe");
customer1.setEmail("john.doe@example.com");
customer1.setAge(30);
customer1.setLocation("New York");


Apply Criteria Restrictions
java
Criteria criteria = session.createCriteria(Customer.class);
criteria.add(Restrictions.between("age", 20, 35));
List<Customer> customersBetween20And35 = criteria.list();


## Dependencies
Include the following dependencies in your `pom.xml`:
xml
<dependencies>
    <dependency>
        <groupId>org.hibernate</groupId>
        <artifactId>hibernate-core</artifactId>
        <version>5.6.14.Final</version>
    </dependency>
    <dependency>
        <groupId>javax.persistence</groupId>
        <artifactId>javax.persistence-api</artifactId>
        <version>2.2</version>
    </dependency>
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.33</version>
    </dependency>
</dependencies>
```

## License
This project is open-source and available under the [MIT License](LICENSE).
