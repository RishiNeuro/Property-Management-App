# Property-Management-App
To clarify the overall architecture:

Backend: Java with Spring Boot (This runs on a server, not on the Android device).
Database: PostgreSQL (Also runs on a server).
Frontend: Kotlin with Jetpack Compose (This runs on the Android device).
The communication between the Android app (frontend) and the server (backend) happens through HTTP requests (typically using JSON for data exchange).

If you were building a web application instead of an Android app, you would use different frontend technologies (like JavaScript with React, Angular, or Vue.js, or Kotlin with a framework like Ktor or JS).

So, to reiterate:

Java/Spring Boot + PostgreSQL: This is your backend and database, running on a server.
Kotlin/Jetpack Compose: This is your Android app (frontend), running on Android devices.
The previous response focused on the initial setup for user authentication, specifically how the Android app (using Kotlin/Compose) would interact with the backend (using Java/Spring Boot) to register users.


______________________________________________________________________________________________________

In a typical client-server architecture (like a mobile app communicating with a server), the "backend" refers to the server-side logic and infrastructure that handles data storage, processing, and business logic. It's the part of the application that users don't directly interact with but is essential for the application to function.   

Components of a Typical Backend:

A backend usually involves several components working together:   

Programming Language: This is the language used to write the server-side logic (e.g., Java, Python, Node.js, Ruby, etc.).   

Framework (Optional but Often Used): A framework provides structure, tools, and libraries to simplify backend development (e.g., Spring Boot for Java, Django/Flask for Python, Express.js for Node.js, Ruby on Rails for Ruby).   

Database: This is where the application's data is stored (e.g., PostgreSQL, MySQL, MongoDB, Oracle, etc.).   

Server: This is the physical or virtual machine that hosts the backend application and makes it accessible over the network.   

How Spring Boot, PostgreSQL, and Java Fit Together:

Java: In your case, Java is the programming language you're using for your backend.
Spring Boot: Spring Boot is a framework that simplifies Java backend development. It provides features like dependency management, auto-configuration, and embedded servers, making it easier to build and deploy Java applications.   
PostgreSQL: PostgreSQL is the database you're using to store your application's data.
Therefore:

Backend is the overall concept: It's the server-side part of your application.
Spring Boot is a tool (framework) used to build the backend with Java.   
PostgreSQL is a tool (database) used by the backend to store data.   
Analogy:

Think of it like building a house:

The house itself is the "backend."
The tools and machinery used to build the house are like "Spring Boot" (framework).
The foundation of the house is like "PostgreSQL" (database).
The construction workers are like "Java" (programming language).
You need all these components to have a functional house (or backend application).

In summary:

You are correct that a backend often requires a database (like PostgreSQL) and a programming language (like Java). Spring Boot is a framework that makes it easier to build Java-based backends that can interact with databases like PostgreSQL. So, while "backend" doesn't exclusively mean Spring Boot, in your current context, you're using Spring Boot to build your backend application, which uses Java and PostgreSQL.   


Sources and related content


_________________________________________________________________________________________________________
1. Access Spring Initializr:f

Open your web browser and navigate to Spring Initializr.

2. Project Details:

Group: Enter a unique identifier for your project (e.g., com.yourcompany).
Artifact: Enter your project name (e.g., property-management-backend).
Package Name: This will be auto-populated based on your Group. You can leave it as is.
Java Version: Choose a compatible version like Java 17 or 11.
3. Dependencies:

Search for and select the following dependencies:

Spring Web: Enables creating a web application.
Spring Data JPA: Simplifies database interaction with JPA.
PostgreSQL Driver: Allows your application to connect to a PostgreSQL database.
Spring Security: Provides security features for user authentication and authorization.
4. Additional Options (Optional):

WebMvc (optional): If you plan to return HTML views in the future, you can select WebMvc.
Lombok (optional): This can reduce boilerplate code (getters, setters, etc.), but it's not strictly necessary.
5. Generate Project:

Click the "Generate" button at the bottom. This will download a compressed file containing your Spring Boot project with the chosen dependencies.

6. Extract and Import Project:

Extract the downloaded zip file.
You can import the project into your preferred IDE (e.g., IntelliJ IDEA, Eclipse) for further development.
Congratulations! You've now set up a basic Spring Boot project with the necessary dependencies for user authentication in your property management application. Now you can proceed with creating your User entity, repository, and other components as outlined in the previous responses.
_______________________________________________________________________________________________________________________________________________________________

You absolutely can use Android Studio for Java backend development, especially for a Spring Boot project. Here's why and how:

Why Android Studio Works for Java Backend:

Based on IntelliJ IDEA: Android Studio is built on top of IntelliJ IDEA Community Edition, which is a powerful IDE for Java development in general.   
Java Support: It has full support for Java, including code completion, refactoring, debugging, and build tools (like Gradle or Maven).
Plugins: You can install plugins in Android Studio to enhance Java development, such as plugins for Spring Boot support.
Steps to Use Android Studio for Your Spring Boot Project:

Import the Project:

Open Android Studio.
Select "Open" or "Import Project".
Navigate to the directory where you extracted the Spring Boot project you generated from Spring Initializr and select the root folder.
Android Studio should recognize it as a Gradle project and import it.
Configure JDK:

Make sure you have a JDK (Java Development Kit) installed. Since you chose Java 17 in Spring Initializr, ensure you have JDK 17 installed.
In Android Studio, go to "File" -> "Project Structure" -> "SDK Location".   
Ensure the "JDK location" is set to your JDK 17 installation directory.
Install Spring Boot Plugins (Recommended):

Go to "File" -> "Settings" -> "Plugins".
Search for "Spring Assistant" and install it. This plugin provides enhanced support for Spring Boot development.
Gradle Sync:

After importing the project, Android Studio will likely prompt you to sync the Gradle files. Click "Sync Now". This will download the project dependencies.
Important Considerations:

Android-Specific Features: Android Studio has many features specific to Android development (like the layout editor, emulator, etc.), which you won't need for your backend project. You can mostly ignore these.
Resource Usage: Android Studio can be resource-intensive, especially if you have both Android and backend projects open simultaneously.   
In summary:

Using Android Studio for your Java Spring Boot backend is perfectly fine, especially since you're already familiar with it. Just remember to configure the JDK correctly and consider installing Spring-related plugins for a better development experience. You can safely ignore the Android-specific features when working on your backend code.


Sources and related content

On 12/28/24, I typed this in the application.properties:
spring.datasource.url=jdbc:postgresql://localhost:5432/
spring.datasource.database=aasra  <-- lowercase "aasra"
spring.datasource.username=postgres
spring.datasource.password=Aasra004

<dependency>
<groupId>org.postgresql</groupId>
<artifactId>postgresql</artifactId>
<version>42.5.0</version> </dependency>

I run the Gradle and pasted the output in the Gemini. Below is the reponse from Gemini:
The output you provided shows that your application successfully started and stopped as expected. Here's a breakdown:

Application Startup:

The logs show the application successfully connecting to the database and initializing all the necessary components.
It starts the Tomcat server on port 8080.
Application Shutdown:

You likely stopped the application using a mechanism like the "Stop" button in your IDE or by interrupting the process.
Gradle recognizes the interruption and displays the "BUILD FAILED" message.
Gradle Build Failure:

The "FAILED" message doesn't necessarily indicate an application error. It simply means that the bootRun task (which runs your application) was interrupted before it could complete normally.
This is a common scenario during development where you might stop the application before it finishes running.

There's nothing to worry about here since the application logs show successful execution. You can safely ignore the "BUILD FAILED" message in this case.


_________________________________________________________________________________________________________
ou're asking for a consolidated version of the user authentication steps I outlined earlier, focusing on the backend (Spring Boot) implementation. Here's a more concise and structured version:

Backend (Spring Boot) User Authentication Steps:

1.Add Spring Security Dependency:

XML

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>

2. Create User Entity:   
Java

@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(unique = true)
    private String username;
    private String password;
    // Other fields (email, roles, etc.)

    // Getters and setters (essential!)
    public Long getId() { return id; }
    public void setId(Long id) { this.id = id;}
    public String getUsername() {return username;}
    public void setUsername(String username) {this.username = username;}
    public String getPassword() {return password;}
    public void setPassword(String password) {this.password = password;}
    //...
}
3. Create User Repository (JPA):

Java

public interface UserRepository extends JpaRepository<User, Long> {
    Optional<User> findByUsername(String username);
}


4. Implement UserDetailsService:

Java

@Service
public class CustomUserDetailsService implements UserDetailsService {

    @Autowired
    private UserRepository userRepository;

    @Override
    public UserDetails loadUserByUsername(String username) throws UsernameNotFoundException {
        User user = userRepository.findByUsername(username)
                .orElseThrow(() -> new UsernameNotFoundException("User not found: " + username));

        return org.springframework.security.core.userdetails.User.builder()
                .username(user.getUsername())
                .password(user.getPassword()) // Password MUST be encoded!
                .roles("USER") // Or fetch roles from the User entity
                .build();
    }
}


5. Configure Password Encoding:

    @Configuration
public class PasswordConfig {
@Bean
public PasswordEncoder passwordEncoder() {
return new BCryptPasswordEncoder();
}
}
```   

6. Configure Spring Security:

Java

@Configuration
@EnableWebSecurity
public class SecurityConfig {

    @Autowired
    private CustomUserDetailsService userDetailsService;

    @Autowired
    private PasswordEncoder passwordEncoder;

    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        http
                .csrf(csrf -> csrf.disable()) // Disable CSRF for simple example. Enable in production!
                .authorizeHttpRequests(authorize -> authorize
                        .requestMatchers("/register", "/login").permitAll() // Allow registration/login
                        .anyRequest().authenticated() // All other endpoints require auth
                )
                .httpBasic(withDefaults()) // Use HTTP Basic for this example
                .formLogin(withDefaults()); // Or use form login

        return http.build();
    }
}


7. Create Registration Endpoint:

Java

@RestController
public class AuthController {

    @Autowired
    private UserRepository userRepository;

    @Autowired
    private PasswordEncoder passwordEncoder;

    @PostMapping("/register")
    public ResponseEntity<String> registerUser(@RequestBody User user) {
        if (userRepository.findByUsername(user.getUsername()).isPresent()) {
            return new ResponseEntity<>("Username is already taken", HttpStatus.BAD_REQUEST);
        }
        user.setPassword(passwordEncoder.encode(user.getPassword()));
        userRepository.save(user);
        return ResponseEntity.ok("User registered successfully");
    }
}
Key Improvements in this Version:

Conciseness: The steps are presented more directly.
Code Completeness: More complete code snippets are provided, including getters/setters in the User entity, the UserRepository, and the PasswordConfig class.
Important Security Note: A comment highlights the importance of enabling CSRF protection in production applications.
Username taken check: Added a check in the register endpoint to ensure that a username is not already taken.
Imports: Remember to include the necessary imports for all classes and annotations.
This refined version should give you a much more solid foundation for implementing user authentication in your Spring Boot backend. Remember to handle exceptions, add input validation, and consider using JWTs for more robust security in a production environment.


Sources and related content
github.com
github.com
medium.com
medium.com
dertompson.com
dertompson.com
github.com
github.com
zebrunner.github.io
zebrunner.github.io






Am I going to perform all the steps you mentioned above (1 to 7) on Android studio? Also, Am I going to use activity_main.xml, emulators or other features of Android studio?




2.0 Flash Experimental. Might not work as expected.
No, you will not perform all the steps I mentioned (1 to 7) directly in Android Studio in the way you're thinking. Those steps are specifically for the backend part of your application, which is a separate Spring Boot project. Android Studio is primarily for Android development (the frontend).

Here's a clearer explanation of where each part goes and how they interact:

Two Separate Projects:

You'll essentially have two separate projects:

Spring Boot Backend Project: This is where you'll implement steps 1-7 (user authentication logic, database interaction, REST APIs). You can create this project using Spring Initializr and open it in an IDE like IntelliJ IDEA or Eclipse.

Android Frontend Project: This is where you'll use Android Studio and develop the user interface, handle user input, and communicate with the Spring Boot backend.

Relationship and Communication:

The Android app (frontend) will communicate with the Spring Boot backend through HTTP requests (using libraries like Retrofit or Volley). The backend will expose REST APIs that the Android app can call for actions like user registration, login, data retrieval, etc.

What You'll Do in Each Project:

Spring Boot Backend (IntelliJ IDEA/Eclipse):

Implement user authentication (steps 1-7).
Create REST endpoints for other app functionalities (e.g., managing properties, tenants).
Set up database connections and data models.
Run the Spring Boot application.
Android Frontend (Android Studio):

Design user interfaces (using XML layouts or Jetpack Compose).
Implement user interactions (button clicks, form submissions).
Use Retrofit/Volley to make HTTP requests to the Spring Boot backend APIs.
Handle responses from the backend (e.g., display data, show error messages).
Use Android components like Activities, Fragments, etc.
Use the emulator or a physical device to test the app.
Example Flow (User Registration):

User interacts with Android app: The user fills out a registration form in the Android app and clicks the "Register" button.

Android app makes HTTP request: The Android app uses Retrofit/Volley to make a POST request to the /register endpoint of the Spring Boot backend, sending the user's data (username, password, etc.) in the request body (usually in JSON format).

Spring Boot backend processes request: The Spring Boot backend receives the request, validates the data, encodes the password, saves the user to the database, and sends a response back to the Android app (e.g., a success message or an error message).

Android app handles response: The Android app receives the response from the backend and updates the UI accordingly (e.g., displays a success message or shows an error message if the registration failed).

Regarding activity_main.xml, emulators, etc.:

You will absolutely use activity_main.xml (or other layout files), emulators (or physical devices), Activities, Fragments, and other Android components in your Android frontend project. These are not relevant to the Spring Boot backend project.

In summary:

Think of it as two separate applications working together: a backend (Spring Boot) and a frontend (Android). The backend provides the data and logic, and the frontend provides the user interface and interacts with the backend through network requests. You will use different IDEs (IntelliJ/Eclipse for Spring Boot, Android Studio for Android) and different tools and technologies for each project.


__________________________________________________________________________________________________________

Excellent! Using IntelliJ IDEA for your Spring Boot backend and Android Studio for your Android frontend is the recommended approach. Here's how to proceed with creating the Spring Boot backend project using Spring Initializr and IntelliJ IDEA:

1. Using Spring Initializr (start.spring.io):

Open your web browser and go to: https://start.spring.io/

Configure the project: Fill out the form with the following settings (or adjust as needed):

Project: Gradle - Groovy or Maven
Language: Java
Spring Boot: Choose a stable version (e.g., the latest stable release)
Group: (Your organization's name or a reverse domain name, e.g., com.example)
Artifact: (The project name, e.g., property-management-backend)
Name: (The project name, e.g., property-management-backend)
Description: (A brief description)
Package name: (The base package for your code, e.g., com.example.propertymanagementbackend)
Packaging: Jar
Java: 17
Add Dependencies: This is crucial. Add the following dependencies:

Spring Web: For building REST APIs
Spring Data JPA: For database interaction
PostgreSQL Driver: For connecting to PostgreSQL
Spring Security: For authentication and authorization
Generate the Project: Click the "GENERATE" button. This will download a zip file containing your project.

2. Importing the Project into IntelliJ IDEA:

Extract the zip file: Extract the downloaded zip file to a convenient location on your computer.

Open IntelliJ IDEA: Launch IntelliJ IDEA.

Import the project:

Click "Open" (or "Import Project" in older versions).
Navigate to the extracted project folder and select the root folder (the one containing the build.gradle or pom.xml file).
Click "OK."
IntelliJ IDEA will now import the project: It will download dependencies, set up the project structure, and create run configurations. This might take a few minutes the first time.

3. Project Structure and Key Files:

After importing, you should see a project structure similar to this:

property-management-backend/
├── build.gradle (or pom.xml)        <-- Build file (Gradle or Maven)
└── src/
    └── main/
        ├── java/
        │   └── com/example/propertymanagementbackend/
        │       ├── PropertyManagementBackendApplication.java  <-- Main application class
        │       └── ... (your code)
        └── resources/
            └── application.properties (or application.yml)  <-- Configuration file
4. Implementing User Authentication (Steps 1-7 from previous response):

Now that you have your Spring Boot project set up in IntelliJ IDEA, you can implement the user authentication logic (steps 1-7 from my previous response). Put the code for the User entity, UserRepository, CustomUserDetailsService, SecurityConfig, and AuthController in the appropriate packages under src/main/java/com/example/propertymanagementbackend/.

5. Configuring the Database Connection:

Add the following properties to your src/main/resources/application.properties file:

Properties

spring.datasource.url=jdbc:postgresql://localhost:5432/aasra  <-- Replace with your database name
spring.datasource.username=postgres
spring.datasource.password=Aasra004
spring.jpa.hibernate.ddl-auto=update  <-- Important for creating/updating DB schema
6. Running the Application:

In IntelliJ IDEA, you should see a green "Run" button next to your main application class (PropertyManagementBackendApplication.java).
Click the "Run" button to start the Spring Boot application.
Check the console output for any errors. If everything is configured correctly, the application should start successfully and you'll see a message like "Started PropertyManagementBackendApplication in X seconds."
Now you have a fully set up Spring Boot backend project in IntelliJ IDEA, ready for you to implement the rest of your backend logic. You can then develop the Android app in Android Studio and connect it to this backend.


_____________________________________________________________________________________________________________________________________________________________

The provided explanation outlines the steps for testing the backend user authentication and highlights some points for developing the Android frontend. Here's a breakdown of each step:

1. Test the Backend (Spring Boot):

1.1 Start your Spring Boot application:

Open your Spring Boot project in IntelliJ IDEA.
Run the application as you normally would (e.g., using the green "Run" button or a shortcut).
1.2 Open Postman:

If you don't have Postman installed, you can download it from https://www.postman.com/
Launch Postman after installation.
1.3 Create a new request:

Click the "+" button to create a new request.
In the "Method" dropdown, select "POST".
In the URL bar, enter the full URL of your registration endpoint, including the port number.
The default port for Spring Boot applications is usually 8080, so the URL might be http://localhost:8080/register.
Double-check your application configuration for the actual port if you've changed it.
1.4 Set the request body:

Click on the "Body" tab.
In the "Body" section, select the "raw" format and choose "JSON" from the dropdown below it.
Paste the following JSON example into the body section, replacing the placeholders with your desired username, password, and email:
JSON

{
  "username": "testuser", // Replace with a unique username
  "password": "testpassword", // Choose a strong password
  "email": "test@example.com" // Provide a valid email address
}
1.5 Send the request:

Click the "Send" button to send the registration request to your backend API.
1.6 Verify the response:

Look at the response code in the top right corner of the Postman window:
Success: If the registration is successful, you should see a 200 OK status code. The response body might be a message like "User registered successfully".
Error (Username already taken): If you try to register with a username that already exists in the database, you should see a 400 Bad Request status code. The response body might contain an error message like "Username is already taken".
1.7 Check the database (Optional):

You can verify that the user was created successfully by directly checking your PostgreSQL database using a tool like pgAdmin or the command line with psql. Ensure the password is stored in an encoded format (not plain text).
Testing Login with HTTP Basic Authentication:

Create an endpoint requiring authentication: If you haven't already, create a simple controller method with a GET request on a path like /hello. This endpoint will require authentication to access.
Make a GET request to the secured endpoint:
In Postman, create a new request (or reuse an existing one).
Set the method to "GET".
Enter the URL of your secured endpoint (e.g., http://localhost:8080/hello).
Set HTTP Basic Authentication:
Go to the "Authorization" tab.
Select "Basic Auth" from the "Type" dropdown.
Enter the username and password of the user you just registered in the respective fields.
Send the request: Click the "Send" button.
Verify the response:
If the credentials are correct, you should receive a 200 OK status code.
Note:

The provided information mentions "Flash Experimental. Might not work as expected." This is likely referring to a temporary or unsupported feature in the context you found it. It's best to disregard it for now.
By following these steps, you can test the basic functionality of your backend user authentication. You can then proceed with developing the Android frontend to interact with the API.






10:10:24 PM: Executing 'bootRun'…



> Task :compileJava

> Task :processResources UP-TO-DATE

> Task :classes

> Task :resolveMainClassName



> Task :bootRun



  .   ____          _            __ _ _

 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \

( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \

 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )

  '  |____| .__|_| |_|_| |_\__, | / / / /

 =========|_|==============|___/=/_/_/_/



 :: Spring Boot ::                (v3.4.1)



2024-12-28T22:10:47.255-06:00  INFO 26492 --- [           main] c.A.p.PropertyManagementAppApplication   : Starting PropertyManagementAppApplication using Java 17.0.12 with PID 26492 (C:\Users\r_sha\AndroidStudioProjects\property-management-App\build\classes\java\main started by r_sha in C:\Users\r_sha\AndroidStudioProjects\property-management-App)

2024-12-28T22:10:47.263-06:00  INFO 26492 --- [           main] c.A.p.PropertyManagementAppApplication   : No active profile set, falling back to 1 default profile: "default"

2024-12-28T22:10:49.097-06:00  INFO 26492 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data JPA repositories in DEFAULT mode.

2024-12-28T22:10:49.240-06:00  INFO 26492 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 119 ms. Found 1 JPA repository interface.

2024-12-28T22:10:50.684-06:00  INFO 26492 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port 8080 (http)

2024-12-28T22:10:50.716-06:00  INFO 26492 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]

2024-12-28T22:10:50.717-06:00  INFO 26492 --- [           main] o.apache.catalina.core.StandardEngine    : Starting Servlet engine: [Apache Tomcat/10.1.34]

2024-12-28T22:10:50.877-06:00  INFO 26492 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext

2024-12-28T22:10:50.880-06:00  INFO 26492 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 3462 ms

2024-12-28T22:10:51.219-06:00  INFO 26492 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Starting...

2024-12-28T22:10:51.742-06:00  INFO 26492 --- [           main] com.zaxxer.hikari.pool.HikariPool        : HikariPool-1 - Added connection org.postgresql.jdbc.PgConnection@9accff0

2024-12-28T22:10:51.747-06:00  INFO 26492 --- [           main] com.zaxxer.hikari.HikariDataSource       : HikariPool-1 - Start completed.

2024-12-28T22:10:51.869-06:00  INFO 26492 --- [           main] o.hibernate.jpa.internal.util.LogHelper  : HHH000204: Processing PersistenceUnitInfo [name: default]

2024-12-28T22:10:52.059-06:00  INFO 26492 --- [           main] org.hibernate.Version                    : HHH000412: Hibernate ORM core version 6.6.4.Final

2024-12-28T22:10:52.150-06:00  INFO 26492 --- [           main] o.h.c.internal.RegionFactoryInitiator    : HHH000026: Second-level cache disabled

2024-12-28T22:10:52.934-06:00  INFO 26492 --- [           main] o.s.o.j.p.SpringPersistenceUnitInfo      : No LoadTimeWeaver setup: ignoring JPA class transformer

2024-12-28T22:10:53.244-06:00  INFO 26492 --- [           main] org.hibernate.orm.connections.pooling    : HHH10001005: Database info:

Database JDBC URL [Connecting through datasource 'HikariDataSource (HikariPool-1)']

Database driver: undefined/unknown

Database version: 17.2

Autocommit mode: undefined/unknown

Isolation level: undefined/unknown

Minimum pool size: undefined/unknown

Maximum pool size: undefined/unknown

2024-12-28T22:10:55.194-06:00  INFO 26492 --- [           main] o.h.e.t.j.p.i.JtaPlatformInitiator       : HHH000489: No JTA platform available (set 'hibernate.transaction.jta.platform' to enable JTA platform integration)

2024-12-28T22:10:55.200-06:00  INFO 26492 --- [           main] j.LocalContainerEntityManagerFactoryBean : Initialized JPA EntityManagerFactory for persistence unit 'default'

2024-12-28T22:10:55.919-06:00  WARN 26492 --- [           main] JpaBaseConfiguration$JpaWebConfiguration : spring.jpa.open-in-view is enabled by default. Therefore, database queries may be performed during view rendering. Explicitly configure spring.jpa.open-in-view to disable this warning

2024-12-28T22:10:55.964-06:00  INFO 26492 --- [           main] r$InitializeUserDetailsManagerConfigurer : Global AuthenticationManager configured with UserDetailsService bean with name customUserDetailsService

2024-12-28T22:10:57.059-06:00  INFO 26492 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port 8080 (http) with context path '/'

2024-12-28T22:10:57.079-06:00  INFO 26492 --- [           main] c.A.p.PropertyManagementAppApplication   : Started PropertyManagementAppApplication in 10.905 seconds (process running for 11.782)

_______________________________________________________________________________________________________________________________________________________________________________________________




