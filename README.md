<!-- Project Logo -->
<br />
<p align="center">
  <img src="arrd_logo_git.png" alt="Logo" width="80" height="80">
  <h3 align="center">Augmented Reality Room Designer</h3>

  <p align="center">
    University Individual Project: AR Room Designer!
    <br />
    <a href="https://youtu.be/KvdZaC-7LEk">View Demo</a>
  </p>
</p>
<br>

<!-- Table of Contents -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Project Links](#project-links)
  * [Tools and Software Used](#tools-and-software-used)
* [Prerequisites](#prerequisites)
* [Installation](#installation)
  * [API](#api-installation)
  * [Android Client](#android-client-installation)
* [Usage](#usage)
  * [API](#api-usage)
  * [Android Client](#android-client-usage)
* [Future](#future)
* [License](#license)
* [Acknowledgements](#acknowledgements)

## About the Project

This project was part of my University Individual Project Module. The task was to find, analyse, design, build and write a disseration about a solution that would help solve a real world problem.

The problem that this project solves is to provide a platform/store were users can advertise and sell their new or unwanted products. One of the key features was Augmented Reality (AR), this allowed users to upload 3D models (in GLTF format) to the server which then can be download by another user in an AR session in runtime.

### Project Links

Since the projects are too large to be uploaded onto this repo their original repos are made public here:

- API : https://github.com/TahmidU/RoomDesignerAPIV1
- Android Client : https://github.com/TahmidU/RoomDesignerClientAndroidV1

### Tools and Software Used

Affinity Design : This was used to design resources to be used as logos, buttons, etc. Not all resources were created by me; some were created using the Image Assest Studio which is under <a href="https://www.apache.org/licenses/LICENSE-2.0">Apache License 2.0</a>.

Adobe XD : This was used to design the prototype GUI.

Visual Paradigm : This was used to produce Entity Relation Diagrams (ERD), Class Diagram (CD), Use Case Diagram (UCD). Visual Paradigm was also used to generate the .ddl file to construct the schema in MySQL (Located in /Database/ of this repo).

Android Studio IDE : This was used to code the android client. It's asset generation and android emulator were awesome and helped speed up the debugging and testing stages.

InteliJ IDE : This was used to code the Spring API.

## Prerequisites

You would need a powerful machine to be able to run both the emulator and the API. It's recommended to have at least 16 GB of RAM (mainly because of the emulator) to comfortably use both, though, 8 GB should suffice.

Java 8 is required for both projects.

## Installation

The following installation guide is for Windows 10. As for other OSes this may vary. 

### API Installation

#### MySQL Community Server

The version that was used for this project was 8.0.18. The link for the download can be found <a href="https://downloads.mysql.com/archives/community/">here</a>. Setup the root user and password and download only the MySQL server.

Once the Environment Variables have been setup below, run the server, create a database called: room_designer_db, exit the shell and copy the schema onto the newly created database: `mysql -u root -p room_designer_db < spring_db.ddl`.

#### Environment Variables

Add the following to path:
- `{MySQL installation path}\MySQL Server 8.0\bin` : This is used to access the mysql shell.

Add the following system variables:
- `ROOM_DESIGNER_DB_CON_USERNAME` and set its value : `root` (or create a user in the database and use that. Not using root is recommended).
- `ROOM_DESIGNER_DB_COND_PASSWORD` and set its value to the users password.
- `ROOM_DESIGNER_SSL_PASSWORD` and set its value : `A4IndvProj`.
- `ROOM_DESIGNER_DB_CON` and set its value : `jdbc:mysql://${MYSQL_HOST:localhost}:3306/room_designer_db?useLegacyDatetimeCode=false&serverTimezone=BST`

#### Dependencies

These are all in the gradle file. These will download and install once you sync gradle:

- Spring Boot Starter Data JPA
- Spring Boot Starter Security
- Spring Boot Starter Web
- Spring Boot Starter Mail
- Auth0 Java JWT
- Tomcat JDBC
- Lombok

### Android Client Installation

#### Emulator

Open the AVD Manager and create new virtual device. Download the system image : Android Q API Level 29 ABI x86.

Download the <a href = "https://github.com/google-ar/arcore-android-sdk/releases">ARCore Simulation Service APK for the emulator</a>. Start the Emulator and drag and drop the ARCore APK into the emulator to begin install the services.

#### Physical Device

**Your device must support ARCore otherwise this would not work!**

If you wish to run the application on your physical android device then ensure that the URL variable in the RetrofitClient.java (located in: /network/api) file matches the IP address of the machine that will be running the API.

**NOTE: I do not take any responsibility of whatever happens to your physical device once you install it.** Though I have tested it several times on my phone and there isn't anything on there that's disruptive, i just wanted to put the disclaimer there.

#### Dependencies

These are all in the gradle file. These will download and install once you sync gradle:

- AndroidX
- RXJava2
- RXAndroid
- OkHTTP
- Picasso
- Retrofit2
- Sceneform (ARCore)
- <a href="https://github.com/cachapa/ExpandableLayout">ExpandableLayout</a>
- <a href="https://github.com/jaiselrahman/FilePicker">File Picker</a>

## Usage

### API Usage
Ensure that the MySQL database is running. Open the project in InteliJ and click the run button.

### Android Client Usage
Click the run button to open the emulator. The app will install on the emulator shortly.

## Future

Though im proud of this project, there's a lot of things that I would like to change, add, and clean-up. This project has taken ~8 months to produce, so I wanted to keep it as a souvenir and be a part of my portfolio.

## License

Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgements

Dr Ross Paterson - For approving this project and supporting me through this project.
