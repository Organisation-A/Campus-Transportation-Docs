## Testing

### logout.test.jsx
This file contains tests for the Logout component utilizing React Testing Library and Jest to validate the component's behavior during user interaction.

#### Purpose
The tests ensure that the Logout component correctly navigates to either the login page or the homepage depending on the user's action.

#### Mocking
- `useNavigate` hook from `react-router-dom` is mocked to control navigation behavior.
- `mapbox-gl` is also mocked as it's not part of the functionality being tested.

### signupForm.test.jsx
This test file contains unit and user acceptance tests for the SignUpForm component.

#### Purpose
The tests verify that the SignUpForm component provides correct user feedback, handles signup successfully, and navigates as expected when users interact with the form.

#### Mocking
- Firebase functions such as `createUserWithEmailAndPassword`, `sendEmailVerification`, and `setDoc` are mocked to isolate behavior.
- Navigation using the `useNavigate` function from `react-router-dom` is mocked.

#### Tests Overview
- **"should display validation error for weak password"**: Unit Test to verify correct password validation.
- **"should handle successful signup"**: Unit Test and User Acceptance Test for smooth signup flow.
- **"navigates to the login page when 'Log In' is clicked"**: Unit Test and User Acceptance Test for navigation verification.

### loginForm.test.jsx
This file contains tests for the LoginForm component.

#### Purpose
The tests verify that the LoginForm component renders correctly, handles password visibility, and manages login attempts.

#### Mocking
- Firebase function `signInWithEmailAndPassword` is mocked.
- `renderWithRouter` is used for simulating a BrowserRouter environment.

#### Tests Overview
- **"renders the login form"**: Unit Test to verify the initial rendering.
- **"allows user to toggle password visibility"**: Unit Test and UAT for password visibility feature.
- **"displays error when login credentials are invalid"**: Unit Test and UAT for failed login feedback.

### Profile.test.jsx
This file contains unit and user acceptance tests for the Profile component.

#### Purpose
The tests verify that the Profile component renders correctly with user details, allows users to reset their password, and handles rental cancellation functionality.

#### Mocking
- Firebase Functions: `auth.onAuthStateChanged` and `getDoc` are mocked.
- Password Reset: `sendPasswordResetEmail` is mocked.
- Axios Requests: Axios post method is mocked to handle rental cancellation.
- Routing: `useNavigate` is mocked for navigation.

#### Tests Overview
- **"renders profile details correctly"**: Unit Test for rendering user details.
- **"shows password reset form when 'Change password' is clicked"**: Unit Test and UAT for displaying the password reset form.
- **"sends reset password email successfully"**: Unit Test and UAT for password reset email success.
- **"displays error when password reset email fails"**: Unit Test and UAT for error handling in password reset.
- **"displays error when rental cancellation fails"**: Unit Test and UAT for rental cancellation failure.
- **"displays error when trying to cancel rental with insufficient KuduBucks"**: Unit Test and UAT for insufficient KuduBucks handling.
- **"toggles password reset form visibility correctly"**: Unit Test for form visibility.
- **"renders correctly with no rental data"**: Unit Test for handling no rental data.

### SearchBar.test.jsx
This file contains unit and user acceptance tests for the SearchBar component.

#### Purpose
The tests verify that the SearchBar component renders correctly, handles search queries, provides autocomplete suggestions, and displays relevant building information.

#### Mocking
- Firestore Functions: Mocking calls to retrieve building data.
- Routing and Navigation: `useNavigate` is mocked for navigation.

#### Tests Overview
- **"renders search bar correctly"**: Unit Test to verify the initial rendering.
- **"displays recent searches when input is focused"**: Unit Test and UAT for recent search display.
- **"provides query suggestions as user types"**: Unit Test and UAT for query suggestions.
- **"displays building details when a search result is selected"**: Unit Test and UAT for building information display.
- **"clears search input when clear icon is clicked"**: Unit Test and UAT for clearing the search input.
- **"handles 'Get Directions' click for selected building"**: Unit Test and UAT for 'Get Directions' functionality.
- **"hides suggestions when input is empty"**: Unit Test for hiding suggestions when input is empty.
- **"displays error when building information retrieval fails"**: Unit Test and UAT for handling errors in data retrieval.
- **"manages dropdown visibility correctly"**: Unit Test for controlling dropdown visibility.

### SideMenu.test.jsx
This file contains unit tests for the SideMenu component.

#### Purpose
The tests verify that the SideMenu component renders correctly, handles navigation properly, and applies the appropriate active class for the selected menu item based on the current route.

#### Mocking
- Navigation Function: `useNavigate` is mocked for navigation actions.
- Routing Simulation: `MemoryRouter` is used to simulate different routes.

#### Tests Overview
- **"navigates to Homepage when Home is clicked"**: Unit Test for navigating to the homepage.
- **"navigates to Bus Schedule when Bus Schedule is clicked"**: Unit Test for navigating to the Bus Schedule.
- **"navigates to Rentals when Rentals is clicked"**: Unit Test for navigating to the Rentals page.
- **"navigates to Profile when Profile is clicked"**: Unit Test for navigating to the Profile page.
- **"navigates to Logout when Logout is clicked"**: Unit Test for navigating to the Logout page.
- **"adds active class for Bus Schedule when pathname is /BusSchedule"**: Unit Test for applying the active class to the Bus Schedule item.
- **"adds active class for Rentals when pathname is /Rentals"**: Unit Test for applying the active class to the Rentals item.
- **"adds active class for Profile when pathname is /Profile"**: Unit Test for applying the active class to the Profile item.
- **"adds active class for Logout when pathname is /Logout"**: Unit Test for applying the active class to the Logout item.

### Homepage.test.jsx
This file contains a unit test for the Homepage component.

#### Purpose
The test verifies that the Homepage component correctly handles navigation when the "Sign out" button is clicked.

#### Mocking
- Navigation Function: `useNavigate` is mocked to simulate navigation behavior.
- Routing Simulation: The component is rendered inside a `Router`.

#### Test Overview
- **"navigates to home page on clicking 'Sign out'"**: Unit Test for verifying navigation after sign-out.

### BusSchedule.test.jsx
This file contains unit and user acceptance tests for the BusSchedule component.

#### Purpose
The tests validate that the BusSchedule component displays bus schedules correctly, allows users to filter routes, downloads the schedule as a PDF, and handles edge cases.

#### Mocking
- Firestore Functions: Mocking `getFirestore`, `collection`, and `getDocs`.
- PDF Download and HTML to Canvas: Mocking `html2canvas` and `jsPDF`.
- Routing Simulation: Component rendered inside a `Router`.

#### Tests Overview
- **"renders the Bus Schedule component"**: Unit Test for rendering the BusSchedule component.
- **"filters bus routes correctly"**: Unit Test for filtering routes.
- **"toggles filter buttons"**: Unit Test for toggling filter buttons.
- **"shows 'No more buses available today' when no upcoming buses"**: Unit Test for handling empty schedules.
- **"downloads the schedule as PDF"**: Unit Test for downloading schedules as PDFs.
- **"downloads schedule as a multi-page PDF"**: Unit Test for handling long schedules.
- **"handles empty response from Firestore gracefully"**: Unit Test for empty Firestore responses.
- **"clicking 'ALL' filter button resets other filters"**: Unit Test for resetting filters.
- **"updates current time every second"**: Unit Test for time updates.
- **"filters bus routes with multiple selected"**: Unit Test for filtering with multiple selections.

### App.test.jsx
This file contains unit and user acceptance tests for the App component.

#### Purpose
The tests aim to ensure that the App component renders the expected UI elements correctly.

#### Mocking
- Routing: `renderWithRouter` is used to simulate routing behavior.

#### Tests Overview
- **"renders App component"**: Unit Test for rendering key UI elements like headings, paragraphs, textboxes, links, and buttons.


