# Student and Courses Management 

In continuation of our integration of Internet Identity login and basic student recording functions, we are now extending our efforts to develop a decentralized application (dApp) focused on managing students and courses. The dApp serves as a comprehensive system to streamline administrative tasks related to educational data. Here's an overview of its functionality:

As we have done to integrate the Internet Identity login and implemented basic student recording functions in our previous coding session level 1 (available here: GitHub link), we will now expand the application to include the following features:
The application allows users to:
Sign In: Users can sign in securely using their DFINITY Internet Identity. (Already integrated in level 1)
Add Students and Courses: Authenticated users can add new students and courses to the system through dedicated forms. 
View Student and Course Lists: The application provides lists of all students and courses currently stored in the system. Users can view these lists to get an overview of the available data.

Assign Courses to Students: Users can assign courses to specific students by selecting a student and a course from dropdown menus and clicking an "Assign Course" button. This action is then processed by the backend, updating the course assignments accordingly.
View Assigned Courses for a Student: After assigning courses to a student, users can view the courses assigned to that student. The application fetches and displays this information dynamically, allowing users to see the courses associated with each student.
Key Functions We Will Utilize:

# 1. App Component

This is a React functional component that represents the main application.
It sets up state variables for managing user authentication, student and course data, forms for adding new students and courses, and selected student and course IDs for assigning courses.
It also initializes an authentication client and manages user sign-in and sign-out functionalities.


# 2. Authentication Functions (signIn, signOut, updateIdentity)

signIn: Initiates the sign-in process using the DFINITY authentication client. Upon successful sign-in, it updates the state to reflect the user's logged-in status and retrieves the user's identity.
signOut: Initiates the sign-out process using the DFINITY authentication client and updates the state to reflect the user's logged-out status.
updateIdentity: Updates the user's identity based on the provided identity parameter. It also creates an actor using an HTTP agent and sets it for the backend service.
# 3. useEffect Hook

It runs once when the component mounts and checks the user's login status. If the user is logged in, it retrieves the stored student and course data from local storage or fetches them from the backend.

# 4. Data Fetching Functions (fetchStudents, fetchCourses, fetchStudentCourses)

These functions make asynchronous calls to the backend to fetch student and course data.
Upon successful fetching, they update the corresponding state variables.
# 5. Add Student and Course Functions (handleAddStudent, handleAddCourse)

These functions handle the submission of new student and course data via forms.
They make asynchronous calls to the backend to add the new data.
Upon successful addition, they update the corresponding state variables and clear the form inputs.

# 6. Course Assignment Function (handleAssignCourseToStudent)

This function handles the assignment of a course to a selected student.
It makes an asynchronous call to the backend to assign the course.
Upon successful assignment, it fetches the updated list of student courses.

# 7. JSX Rendering
   
The JSX code renders different UI elements based on the user's authentication status and interactions.
It displays different components such as sign-in/sign-out buttons, forms for adding students and courses, dropdowns for selecting students and courses, and lists of students, courses, and student courses.

# 9. Event Handlers
    
Event handlers are attached to various UI elements like buttons and form inputs to handle user interactions such as signing in, signing out, adding students and courses, and assigning courses to students.

