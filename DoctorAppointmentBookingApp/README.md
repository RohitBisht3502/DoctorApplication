# <h1 align = "center"> Doctor Application API </h1>
___ 
<p align="center">
<a href="Java url">
    <img alt="Java" src="https://img.shields.io/badge/Java->=8-darkblue.svg" />
</a>
<a href="Maven url" >
    <img alt="Maven" src="https://img.shields.io/badge/maven-4.0-brightgreen.svg" />
</a>
<a href="Spring Boot url" >
    <img alt="Spring Boot" src="https://img.shields.io/badge/Spring Boot-3.1.3-brightgreen.svg" />
</a>
    <img alt = "License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
    </a>
</p>


---

<p align="left">

## Overview

The Online Doctor Appointment Booking System is a sophisticated and user-friendly web application built using the Spring Boot framework, designed to streamline the process of scheduling and managing appointments with healthcare professionals. This project leverages the power of modern technology to enhance the efficiency of healthcare services and improve the overall patient experience.

## Technologies Used

- **Framework:** Spring Boot
- **Language:** Java
- **Build Tool:** Maven
- **Database:** MySql
---
## Data Flow
1. **Patient Registration:** Data flow from Patients to the Patient Data Store when registering.
2. **Doctor Registration:** Data flow from Doctors to the Doctor Data Store when registering.
3. **Appointment Request:** Data flow from Patients to the Appointment Booking process.
4. **Appointment Confirmation:** Data flow from the Appointment Booking process to Doctors.
5. **Appointment Cancellation:** Data flow from Patients to the Appointment Management process.
6. **Appointment Rescheduling:** Data flow from Patients to the Appointment Management process.
7. **Appointment Details:** Data flow from Appointment Data Store to Patients, Doctors, and Administrators for appointment information.
---
### Model
1. **Doctor:**
2. **Patient:**
3. **Appointment:**
4. **PatientAuthenticationToken:**
 ->This Patient Token is only for when a patient book an appointment so they will get token in their register email.

### Controller

The Controller layer is responsible for handling incoming HTTP requests and delegating them to the appropriate services. It defines API endpoints for the following operations:

1. **Admin Controller:** `API for admin usage`
   
   This endpoint retrieves a list of all registered Admins.

   ```java
    @GetMapping("patients")
    public List<Patient> getAllPatients()
    {
    }

    @PostMapping("doctor")
    public String addDoctor(@RequestBody Doctor newDoctor)
    {
    }

    @GetMapping("patients/bloodGroup/{bloodGroup}")
    public List<Patient> getAllPatientsByBloodGroup(@PathVariable BloopGroup bloodGroup)
    {
    }
   ```

2. **Doctor Controller:** `API for Doctor usage`

   This endpoint retrieves detailed information about a specific Doctor.

   ```java
   @GetMapping("doctors")
    public List<Doctor> getAllDoctors(@Valid @RequestBody AuthenticationInputDto authInfo)
    {
    }


    @GetMapping("doctor/{id}")
    public Doctor getDoctorById(@PathVariable Integer id)
    {
    }
   ```

3. **Patient Controller:** `API's are like book an appointment,signin,sinup,etc`

   This endpoint adds a new restaurant to the system.

   ```java
      @Autowired
    PatientService patientService;

    @Autowired
    AppointmentService appointmentService;

    @Autowired
    DoctorService doctorService;


    //sign up
    @PostMapping("patient/signup")
    public String patientSignUp(@Valid @RequestBody Patient patient)
    {
        return patientService.patientSignUp(patient);
    }



    //sign in
    @PostMapping("patient/signIn")
    public String patientSignIn(@RequestBody SignInInputDto signInInput)
    {
        return patientService.patientSignIn(signInInput);
    }


    //sign out
    @DeleteMapping("patient/signOut")
    public String patientSignOut(@RequestBody AuthenticationInputDto authInfo)
    {
        return patientService.patientSignOut(authInfo);
    }


    //schedule an appointment

    @PostMapping("patient/appointment/schedule")
    public String scheduleAppointment(@RequestBody ScheduleAppointmentDTO scheduleAppointmentDTO)
    {
    }

    @DeleteMapping("patient/appointment/{appointmentId}/cancel")
    public String cancelAppointment(@RequestBody AuthenticationInputDto authInfo, @PathVariable Integer appointmentId)
    {
    }

    @GetMapping("doctors/qualification/{qual}/or/specialization/{spec}")
    public List<Doctor> getDoctorsByQualificationOrSpec(@RequestBody AuthenticationInputDto authInfo,@PathVariable Qualification qual,@PathVariable Specialization spec)
    {
    }
   ```
### Services
The Services layer implements the core business logic, data processing, and interaction with the data repository. Key responsibilities include:

- Validating input data.
- Performing CRUD operations on restaurant data.
- Handling data transformations and interactions with external systems (if applicable).
  
1. **Doctor Service:**
2. **Patient Service:**
3. **Appointment Service:**
4. **PatientAuthenticationToken Service:**

### Repository

The Repository layer manages data access to the underlying database. It handles database operations such as Create, Read, Update, and Delete (CRUD) for patient,doctor and token data etc. Additionally, it may include data mapping and conversion between Java objects and database entities.

## Data Structures Used

The project utilizes the following data structures:

### Restaurant Class

The `Restaurant` class defines the structure for restaurant data and includes the following fields:

- `restaurantId` (Restaurant ID): An integer that serves as a unique identifier for each restaurant.
- `restaurantName` (Restaurant Name): A string representing the restaurant's name.
- `restaurantAddress` (Restaurant Address): A string containing the restaurant's address.
- `restaurantContact` (Restaurant Contact): A string representing the restaurant's contact number (e.g., 911234567890).
- `restaurantEmail` (Restaurant Email): A string containing the restaurant's email address.
- `restaurantSpecialty` (Restaurant Specialty): A string representing the restaurant's specialty.
- `numberOfStaff` (Number of Staff): An integer indicating the number of staff members.
- `restaurantType` (Restaurant Type): An enumeration specifying the restaurant type (e.g., FAMILY, CAFE, FAST_FOOD).

### Type Enum

The `Type` enum enumerates the possible restaurant types:

- `Gender`: Represents a patient gender.
- `Qualification`: Represents a doctor's qualification.
- `Specialization`: Represents a type of doctor.
- `BloopGroup`: Represents a blood group of patient like AB+,B+,AB-.
- ...
## Project Summary

The Restaurant Management Application is a robust Spring Boot application designed for efficient restaurant data management. It offers a set of RESTful API endpoints for various restaurant-related operations, including adding, retrieving, updating, and deleting restaurant information.

Key Features:

- Streamlines appointment booking, reducing wait times and enhancing patient satisfactionand doctor also.
- Data validation to ensure data integrity.
- Clean code separation with a layered architecture (Controller, Services, Repository).
- Robust error handling for improved reliability.
- Java-based backend and Maven for build management.

The Online Doctor Appointment Booking System developed with Spring Boot is a game-changer for both patients and healthcare providers. By simplifying appointment scheduling, increasing transparency, and enhancing overall patient care, this system represents a significant leap forward in modern healthcare.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

Thank you to the Spring Boot and Java communities for providing excellent tools and resources.

## Contact
For questions or feedback, please contact [Rohit singh bisht](mailto:business.rohitbisht3502@gmail.com)
