# **Campus Course & Records Manager (CCRM)**

### **Project Summary**

The Campus Course & Records Manager (CCRM) is a robust, console-based Java application designed to streamline student and course administration for an educational institution. This project is built using Java SE and is configured to connect with an Oracle database for persistent data storage.

This application demonstrates a comprehensive understanding of core Java principles, including object-oriented programming (OOP), modern I/O with NIO.2, and JDBC for database connectivity. It also incorporates key design patterns to ensure a clean and scalable architecture.

### **Key Features**

* **Student Management**: Efficiently add, list, update, and track student academic records and status.  
* **Course & Instructor Management**: Create new courses, update existing ones, and assign instructors.  
* **Enrollment & Grading**: Handle student enrollments and unenrollments with built-in academic rule enforcement, such as credit limits. Record grades and generate detailed academic transcripts.  
* **Data Handling**: Import and export data in CSV format and create timestamped backups of all application data.

### **How to Get Started**

To compile and run the CCRM application from your command line, you must have the following prerequisites installed:

* **Java Development Kit (JDK)**: Version 11 or newer.  
* **Oracle Database**: The application requires an Oracle database connection.

**Installation Steps:**

1. **Clone the project repository:**  
   git clone https://github.com/Pratheekneemkar/CCRM.git

2. **Compile the source code:** From the project's root directory, run the following command to compile all source files and include the Oracle JDBC driver in the classpath.  
   javac \-d bin \-cp "lib/ojdbc17.jar" src/edu/ccrm/cli/\*.java src/edu/ccrm/config/\*.java src/edu/ccrm/domain/\*.java src/edu/ccrm/exception/\*.java src/edu/ccrm/io/\*.java src/edu/ccrm/service/\*.java src/edu/ccrm/util/\*.java

3. **Database Setup:** Connect to your Oracle database with administrative privileges and create the required user by executing the following SQL commands:  
   CREATE USER ccrm\_user IDENTIFIED BY ccrm\_pass;  
   GRANT CONNECT, RESOURCE, DBA TO ccrm\_user;

   The application will automatically create the necessary tables on its first run.  
4. **Run the application:** Once compiled, run the application from the root directory, making sure both the bin folder and the JDBC driver are on the classpath.  
   java \-cp "bin;lib/ojdbc17.jar" edu.ccrm.cli.Main

   The application will then start, and you will be presented with a command-line interface.

### **Technical Implementation**

This project effectively demonstrates several key Java concepts and design patterns:

* **Core Principles**: The application is built upon fundamental OOP principles, including **Encapsulation** (private fields with public getters/setters in Student.java and Course.java), **Inheritance** (Student and Instructor extending Person.java), and **Polymorphism** (using Person references in TranscriptService.java).  
* **Modern Java Features**: It leverages modern I/O capabilities with NIO.2 for file operations and incorporates **Lambda Expressions** to streamline data filtering in CourseService.java.  
* **Design Patterns**: The project implements the **Singleton Design Pattern** in AppConfig.java to manage a single configuration instance and the **Builder Design Pattern** in Course.java for flexible object creation.  
* **Error Handling**: The application includes custom exceptions like DuplicateEnrollmentException.java and MaxCreditLimitExceededException.java for robust error handling.

### **Understanding the Java Platform**

| Term | Full Name | Description |
| :---- | :---- | :---- |
| **JVM** | Java Virtual Machine | An abstract machine that provides a runtime environment for executing Java bytecode. |
| **JRE** | Java Runtime Environment | A software package that contains the JVM and the necessary libraries to **run** Java applications. |
| **JDK** | Java Development Kit | A superset of the JRE that includes everything needed to **develop** Java applications, such as the javac compiler and debugger. |
| **Java ME** | Micro Edition | A subset of Java APIs for mobile devices and embedded systems. |
| **Java SE** | Standard Edition | The core Java platform for desktop and server applications. |
| **Java EE** | Enterprise Edition | A superset of Java SE with additional APIs for large-scale enterprise applications. |

### **IDE Setup**

For development, you can easily set up the project in your preferred Integrated Development Environment (IDE):

* **Eclipse**: Use "File \> Import \> General \> Existing Projects into Workspace" and then add the lib/ojdbc17.jar to the project's build path under "Project \> Build Path \> Configure Build Path."  
* **Visual Studio Code**: Install the "Extension Pack for Java," open the project folder, and add the lib/ojdbc17.jar by clicking the plus icon next to "Referenced Libraries" in the "JAVA PROJECTS" explorer view.

### **Acknowledgements**

This project was developed for the "Programming in Java" course on the Vityarthi portal. All code is original work by Neemkar Sai Pratheek.
