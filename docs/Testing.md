## Testing

### logout.test.jsx
This file contains tests for the Logout component utilizing React Testing Library and Jest to validate the component's behavior during user interaction. The primary objective is to confirm that the component navigates correctly based on user choices.

#### Purpose:
The tests ensure that the Logout component correctly navigates to either the login page or the homepage depending on whether the user chooses to log out or cancels the action.

#### Mocking:
The useNavigate hook from react-router-dom is mocked to control navigation behavior allowing verification without actual page redirection.
mapbox-gl is also mocked since the Logout component uses it but it's not part of the functionality being tested.

### signupForm.test.jsx
This test file contains unit and user acceptance tests for the SignUpForm component. The tests use React Testing Library and Jest to validate the component's behavior during various user interactions focusing on form validation signup flow and navigation.

#### Purpose:
The tests verify that the SignUpForm component provides correct user feedback handles signup successfully and navigates as expected when users interact with the form.

#### Mocking:
- Firebase Functions: The Firebase functions (createUserWithEmailAndPassword sendEmailVerification setDoc) are mocked to isolate the component's behavior without real API calls.
- Navigation: The useNavigate function from react-router-dom is mocked to validate navigation without actual redirection.

#### Tests Overview:
- **"should display validation error for weak password"**:
  - Type: Unit Test
  - Purpose: This unit test verifies that the component correctly handles password validation.
  - Behavior Tested: When a weak password is entered it checks that the validation error message is displayed and createUserWithEmailAndPassword is not called.
  
- **"should handle successful signup"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: The test is both a unit test for the signup logic and a user acceptance test to ensure a smooth user flow.
  - Behavior Tested: It simulates a successful signup flow including submitting valid information verifying if createUserWithEmailAndPassword sendEmailVerification and setDoc are called appropriately and confirming the success message is displayed.
  
- **"navigates to the login page when 'Log In' ### is clicked"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: This test ensures that the user can navigate to the login page.
  - Behavior Tested: It checks if clicking the "Log In" link triggers the navigation to the login page ('/').

### loginForm.test.jsx
This file contains unit and user acceptance tests for the LoginForm component. The tests use React Testing Library and Jest to validate how the component behaves during different user interactions specifically focusing on rendering password visibility and login functionality.

#### Purpose:
The tests verify that the LoginForm component renders correctly handles password visibility and manages login attempts (both successful and unsuccessful).

#### Mocking:
- Firebase Functions: The signInWithEmailAndPassword function from Firebase is mocked to simulate login behavior without making real network requests.
- Routing: renderWithRouter is used to wrap the component in a BrowserRouter simulating a real browser environment for routing purposes.

#### Tests Overview:
- **"renders the login form"**:
  - Type: Unit Test
  - Purpose: Ensures that the LoginForm component renders properly with the email input password input and sign-in button present.
  - Behavior Tested: Verifies the initial rendering of the form to confirm that all expected elements are in place.

- **"allows user to toggle password visibility"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: This test checks that users can toggle password visibility using the icon.
  - Behavior Tested: Initially the password should be hidden. Clicking the toggle icon changes the type of the password input from "password" to "text" and vice versa. As a UAT it confirms that the component provides expected behavior for user convenience.
  
- **"displays error when login credentials are invalid"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: Tests the login flow when incorrect credentials are provided.
  - Behavior Tested: Mocks a rejected signInWithEmailAndPassword call resulting in an error toast message. As a UAT it ensures that the user gets appropriate feedback when their login attempt fails.

### Profile.test.jsx
This file contains unit and user acceptance tests for the Profile component. The tests use React Testing Library and Jest to validate how the component behaves during different user interactions specifically focusing on rendering user details password reset functionality and managing rental operations.

#### Purpose:
The tests verify that the Profile component renders correctly with user details allows users to reset their password and handles rental cancellation functionality. The component's behaviour is validated both with and without user data ensuring proper error handling and feedback.

#### Mocking:
- Firebase Functions: The `auth.onAuthStateChanged` function is mocked to simulate user authentication and `getDoc` is mocked to retrieve user data from Firestore.
- Password Reset: The `sendPasswordResetEmail` function is mocked to simulate the password reset flow.
- Axios Requests: The Axios post method is mocked to handle rental cancellation without making actual HTTP requests.
- Routing: The `useNavigate` function is mocked to simulate navigation within the component.

#### Tests Overview:
- **"renders profile details correctly"**:
  - Type: Unit Test
  - Purpose: Ensures that the Profile component renders user details correctly.
  - Behavior Tested: Verifies the presence of the user's full name email and KuduBucks after successful data retrieval.

- **"shows password reset form when 'Change password' is clicked"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: Tests that the password reset form appears when the "Change password" link is clicked.
  - Behavior Tested: Verifies that clicking the link opens the password reset form. As a UAT it confirms that the component responds appropriately to the user's request to reset their password.

- **"sends reset password email successfully"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: Tests that a password reset email is sent successfully when the reset form is submitted.
  - Behavior Tested: Mocks a successful `sendPasswordResetEmail` function call and confirms the display of a success message.

- **"displays error when password reset email fails"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: Tests the behaviour when the password reset email fails to send.
  - Behavior Tested: Mocks a rejected `sendPasswordResetEmail` call to ensure an error message is displayed. As a UAT it confirms the user receives appropriate feedback when a password reset fails.

- **"displays error when rental cancellation fails"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: Tests the behaviour when the rental cancellation fails due to an error.
  - Behavior Tested: Mocks a failed Axios post request when attempting to cancel a rental and verifies the appearance of an error toast message to notify the user of the failure.

- **"displays error when trying to cancel rental with insufficient KuduBucks"**:
  - Type: Unit Test and User Acceptance Test (UAT)
  - Purpose: Tests that the component correctly handles scenarios where the user attempts to cancel a rental with insufficient KuduBucks.
  - Behavior Tested: Mocks the user’s profile with insufficient KuduBucks and verifies that an appropriate error message is displayed when attempting to cancel a rental.

- **"toggles password reset form visibility correctly"**:
  - Type: Unit Test
  - Purpose: Tests that the password reset form can be toggled correctly by clicking the "Change password" and "Cancel" buttons.
  - Behavior Tested: Verifies that the password reset form is shown when requested and hidden when cancelled.

- **"renders correctly with no rental data"**:
  - Type: Unit Test
  - Purpose: Ensures that the Profile component displays correctly when the user has no current rental.
  - Behavior Tested: Verifies that the component displays "No current rental" when there is no active rental data for the user.

### SearchBar.test.jsx
This file contains unit and user acceptance tests for the SearchBar component. The tests use React Testing Library and Jest to validate how the component behaves during different user interactions, specifically focusing on search functionality, query suggestions, and the integration with building information.

#### Purpose:
The tests verify that the SearchBar component renders correctly, handles search queries, provides autocomplete suggestions, and displays relevant building information. Additionally, the tests ensure that recent searches are handled properly, and elements are displayed as expected during different interactions.
#### Mocking:
- Firestore Functions: Firestore calls are mocked to simulate retrieving building data without making actual requests to the Firestore database.
- Routing and Navigation: The useNavigate function from react-router-dom is mocked to simulate navigation for directing users to specific building locations.
- Search Suggestions: Functions related to fetching recent searches or query suggestions are mocked to simulate user data.
####  Tests Overview:
-**"renders search bar correctly"**
    - Type: Unit Test
    - Purpose: Ensures that the SearchBar component renders properly with the input field and necessary buttons present.
    - Behavior Tested: Verifies the initial rendering of the search input field, clear icon, and search button to confirm that all expected elements are in place.
- **"displays recent searches when input is focused"**
    - Type: Unit Test and User Acceptance Test (UAT)
    - Purpose: Tests that recent searches are displayed when the user focuses on the search input field.
    - Behavior Tested: Verifies that focusing on the input field triggers the display of recent search items. As a UAT, it ensures that users can see and select from their previous searches conveniently.
- **"provides query suggestions as user types"**
    - Type: Unit Test and User Acceptance Test (UAT)
    - Purpose: Tests that query suggestions are displayed as the user types into the search bar.
    - Behavior Tested: Mocks a list of building names and confirms that matching suggestions are displayed based on the user's input. As a UAT, it ensures that users receive dynamic suggestions, enhancing search efficiency.
- **"displays building details when a search result is selected"**
    - Type: Unit Test and User Acceptance Test (UAT)
    - Purpose: Tests that building details are displayed correctly when a search result is selected.
    - Behavior Tested: Verifies that selecting a suggested building name from the dropdown displays relevant building information, such as description and directions link. As a UAT, it ensures that the user gets useful information upon selecting a building.
- **"clears search input when clear icon is clicked"**
    - Type: Unit Test and User Acceptance Test (UAT)
    - Purpose: Tests that the search input is cleared when the clear icon is clicked.
    - Behavior Tested: Mocks the clear button click event and checks that the input field becomes empty, confirming proper functionality for resetting searches. As a UAT, it confirms that users can easily clear their search queries.
- **"handles 'Get Directions' click for selected building"**
    - Type: Unit Test and User Acceptance Test (UAT)
    - Purpose: Tests that clicking the "Get Directions" button navigates the user to the relevant building's location.
    - Behavior Tested: Mocks the navigation function and verifies that it is called with the correct building route, confirming the proper direction feature. As a UAT, it ensures that users are correctly guided to the building.
- **"hides suggestions when input is empty"**
    - Type: Unit Test
    - Purpose: Ensures that suggestions are hidden when the search input is cleared or left empty.
    - Behavior Tested: Verifies that the suggestion dropdown is not visible when there is no input, providing a clean and intuitive user experience.
- **"displays error when building information retrieval fails"**
    - Type: Unit Test and User Acceptance Test (UAT)
    - Purpose: Tests that an appropriate error message is displayed when the building information fails to load.
    - Behavior Tested: Mocks a failure in fetching building details from Firestore and verifies that an error message is shown, ensuring that users are informed if something goes wrong during the search.
- **"manages dropdown visibility correctly"**
    - Type: Unit Test
    - Purpose: Tests the visibility of the suggestions dropdown based on user actions like typing and clicking outside the search bar.
    - Behavior Tested: Verifies that the dropdown appears when the user starts typing and disappears appropriately when not in use, ensuring an effective and clean UI.



### SideMenu.test.jsx
This file contains unit tests for the SideMenu component. The tests use React Testing Library and Jest to validate the component's behavior during navigation and to ensure that the correct menu item is marked as active based on the current route.
#### Purpose:
The tests verify that the SideMenu component renders correctly, handles navigation properly when different menu items are clicked, and applies the appropriate active class for the selected menu item based on the current route.
#### Mocking:
- Navigation Function: The useNavigate function from react-router-dom is mocked to simulate the navigation actions without requiring actual routing during the tests.
- Routing Simulation: The MemoryRouter is used to simulate different routes and initial paths to test how the SideMenu behaves depending on the current route.
####  Tests Overview:
- **"navigates to Homepage when Home is clicked"**
    - Type: Unit Test
    - Purpose: Ensures that clicking the "Home" button triggers navigation to the homepage.
    - Behavior Tested: Verifies that the mocked navigate function is called with the /Homepage route when the "Home" button is clicked.
- **"navigates to Bus Schedule when Bus Schedule is clicked"**
    - Type: Unit Test### 
    - Purpose: Tests that clicking the "Bus Schedule" button navigates to the correct page.
    - Behavior Tested: Confirms that navigate is called with /BusSchedule, indicating proper routing behavior.
- **"navigates to Rentals when Rentals is clicked"**
    - Type: Unit Test
    - Purpose: Ensures that clicking the "Rentals" button triggers navigation to the rentals page.
    - Behavior Tested: Verifies that navigate is called with /Rentals, validating the correct page transition.
- **"navigates to Profile when Profile is clicked"**
    - Type: Unit Test
    - Purpose: Ensures that clicking the "Profile" button navigates the user to their profile page.
    - Behavior Tested: Checks that navigate is called with /Profile, demonstrating that the navigation works as expected.
- **"navigates to Logout when Logout is clicked"**
    - Type: Unit Test
    - Purpose: Ensures that clicking the "Logout" button triggers navigation to the logout page.
    - Behavior Tested: Confirms that navigate is called with /Logout, indicating proper routing functionality.
- **"adds active class for Bus Schedule when pathname is /BusSchedule"**
    - Type: Unit Test
    - Purpose: Verifies that the "Bus Schedule" menu item receives the active class when the current path is /BusSchedule.
    - Behavior Tested: Checks that the menu item for "Bus Schedule" has the active class when it is the current route, ensuring proper visual feedback for the active link.
- **"does not add active class for Bus Schedule when pathname is not /BusSchedule"**
    - Type: Unit Test
    - Purpose: Ensures that the "Bus Schedule" menu item does not have the active class when it is not the current path.
    - Behavior Tested: Confirms that the "Bus Schedule" menu item is not marked as active when on a different route.
- **"adds active class for Rentals when pathname is /Rentals"**
    - Type: Unit Test
    - Purpose: Verifies that the "Rentals" menu item is marked as active when the path is /Rentals.
    - Behavior Tested: Checks that the active class is applied correctly when the "Rentals" page is selected.
- **"does not add active class for Rentals when pathname is not /Rentals"**
    - Type: Unit Test
    - Purpose: Ensures that the "Rentals" menu item is not marked as active if the current path is different.
    - Behavior Tested: Confirms that the menu item for "Rentals" does not have the active class when on a different route.
- **"adds active class for Profile when pathname is /Profile"**
    - Type: Unit Test
    - Purpose: Verifies that the "Profile" menu item receives the active class when the current route is /Profile.
    - Behavior Tested: Ensures proper visual feedback for the active link on the "Profile" page.
- **"does not add active class for Profile when pathname is not /Profile"**
    - Type: Unit Test
    - Purpose: Ensures that the "Profile" menu item is not active if it is not the current route.
    - Behavior Tested: Confirms that the "Profile" menu item does not have the active class when the user is on another route.
- **"adds active class for Logout when pathname is /Logout"**
    - Type: Unit Test
    - Purpose: Verifies that the "Logout" menu item is marked as active when the route is /Logout.
    - Behavior Tested: Checks that the logout option is correctly marked as active when navigating to the logout page.
- **"does not add active class for Logout when pathname is not /Logout"**
    - Type: Unit Test
    - Purpose: Ensures that the "Logout" menu item does not have the active class when the current path is different.
    - Behavior Tested: Confirms that the "Logout" menu item is not highlighted if it is not the current route.
These tests ensure that navigation is properly handled for each menu item and that the correct visual indication is provided for the active page, contributing to an intuitive user experience when interacting with the SideMenu component.


### Homepage.test.jsx
This file contains a unit test for the Homepage component. The test uses React Testing Library and Jest to validate the component's behavior when the user interacts with the "Sign out" button.
#### Purpose:
The test verifies that the Homepage component correctly handles navigation when the "Sign out" button is clicked, ensuring that users are redirected appropriately.
#### Mocking:
- Navigation Function: The useNavigate function from react-router-dom is mocked to simulate navigation behaviour without actually routing during the test.
- Routing Simulation: The component is rendered inside a Router to provide the necessary routing context.
Test Overview:
- **"navigates to home page on clicking 'Sign out'"**
    - Type: Unit Test
    - Purpose: Ensures that clicking the "Sign out" button triggers navigation to the home page.
    - behaviour Tested: Verifies that the mocked navigate function is called with the / route when the "Sign out" button is clicked. This ensures that the application redirects the user to the login or home screen after logging out.
This test is essential to validate the sign-out functionality, ensuring that users can effectively log out and are redirected to the appropriate page afterward.


### BusSchedule.test.jsx
This file contains unit and user acceptance tests for the BusSchedule component. The tests use React Testing Library and Jest to verify how the component behaves during different user interactions, including rendering, filtering routes, and downloading the schedule as a PDF.
#### Purpose:
The tests validate that the BusSchedule component displays bus schedules correctly, allows users to filter routes, downloads the schedule as a PDF, and handles edge cases such as empty Firestore responses or missing upcoming buses.
#### Mocking:
- Firebase Firestore: The Firestore functions (getFirestore, collection, getDocs) are mocked to simulate fetching bus schedule data without making real network requests.
- Firebase Auth: getAuth is mocked to simulate authentication state.
- PDF Download and HTML to Canvas: Both html2canvas and jsPDF are mocked to avoid real canvas rendering and PDF generation, making the tests faster and isolated.
- Routing Simulation: The component is rendered inside a Router to simulate a browser environment for routing purposes.
####  Tests Overview:
- **"renders the Bus Schedule component"**
    - Type: Unit Test
    - Purpose: Ensures that the BusSchedule component renders correctly, including elements like "Bus Schedule" title and filter buttons.
    - Behavior Tested: Verifies initial rendering to confirm that all expected elements, such as filter buttons, are present.
- **"filters bus routes correctly"**
    - Type: Unit Test
    - Purpose: Tests that bus routes can be filtered by clicking on specific filter buttons.
    - Behavior Tested: Simulates a click on the "Full Circuit" filter button and verifies that the appropriate route is displayed.
- **"toggles filter buttons"**
    - Type: Unit Test
    - Purpose: Verifies that the filter buttons can be toggled on and off.
    - Behavior Tested: Simulates clicking on a filter button, checks the applied style, and ensures that clicking it again removes the active style.
- **"shows 'No more buses available today' when no upcoming buses"**
    - Type: Unit Test
    - Purpose: Tests how the component handles cases where no buses are scheduled for the day.
    - Behavior Tested: Ensures that the text "No more buses available today" is shown if no upcoming buses are found.
- **"downloads the schedule as PDF when 'Download Schedule as PDF' button is clicked"**
    - Type: Unit Test
    - Purpose: Ensures the schedule can be downloaded as a PDF when the download button is clicked.
    - Behavior Tested: Mocks html2canvas and verifies that it is called, simulating the PDF download behavior.
- **"downloads schedule as a multi-page PDF"**
    - Type: Unit Test
    - Purpose: Verifies that the schedule can be downloaded across multiple PDF pages if it's too long.
    - Behavior Tested: Mocks html2canvas with a large canvas and checks the correct behavior for multi-page PDF generation.
- **"handles empty response from Firestore gracefully"**
    - Type: Unit Test
    - Purpose: Ensures that the component behaves gracefully when Firestore returns no data.
    - Behavior Tested: Mocks an empty response from Firestore and verifies that the "No more buses available today" message is shown.
- **"clicking 'ALL' filter button resets other filters"**
    - Type: Unit Test
    - Purpose: Tests that selecting the "ALL" filter button resets all other filters.
    - Behavior Tested: Clicks on multiple filter buttons and then clicks "ALL", ensuring all other filters are reset.
- **"updates current time every second"**
    - Type: Unit Test
    - Purpose: Tests the updating of the current time every second.
    - Behavior Tested: Uses Jest's fake timers to simulate time passing and verifies that the displayed time updates accordingly.
- **"filters bus routes with multiple selected"**
    - Type: Unit Test
    - Purpose: Tests that multiple route filters can be selected simultaneously.
    - Behavior Tested: Simulates selecting multiple route filters and verifies that the correct routes are displayed and styled differently.


### App.test.jsx
This file contains unit and user acceptance tests for the App component. The tests use React Testing Library and Jest to validate the presence of key elements in the component, focusing on different roles such as headings, paragraphs, textboxes, links, and buttons.
#### Purpose:
The tests aim to ensure that the App component renders the expected UI elements correctly when loaded, providing basic coverage for the presence of key interactive or display components.
#### Mocking:
- Routing: The renderWithRouter function is used to render the component within a Router context, allowing for routing-related behavior to be simulated.
####  Tests Overview:
- **"renders App component"**
    - Type: Unit Test
    - Purpose: Ensures that the App component renders properly by verifying the presence of core UI elements such as headings, paragraphs, buttons, textboxes, and links.
    - Behavior Tested:
        - Checks for a heading using getByRole('heading') to verify that an appropriate heading element is present in the DOM.
        - Verifies the presence of a paragraph element by using getByRole('paragraph').
        - Looks for a textbox element to confirm that an input field or similar text input element is available.
        - Checks for a link to ensure that navigation links are properly rendered.
        - Verifies the existence of a button to confirm the availability of actionable elements.
These basic checks help to validate the initial rendering of the key components within the App and provide a foundation for further testing as the project evolves.