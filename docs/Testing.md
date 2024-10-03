## Testing

logout.test.jsx
This file contains tests for the Logout component, utilizing React Testing Library and Jest to validate the component's behavior during user interaction. The primary objective is to confirm that the component navigates correctly based on user choices.

Purpose:
The tests ensure that the Logout component correctly navigates to either the login page or the homepage, depending on whether the user chooses to log out or cancels the action.

Mocking:
The useNavigate hook from react-router-dom is mocked to control navigation behavior, allowing verification without actual page redirection.
mapbox-gl is also mocked since the Logout component uses it, but it's not part of the functionality being tested.


signupForm.test.jsx
This test file contains unit and user acceptance tests for the SignUpForm component. The tests use React Testing Library and Jest to validate the component's behavior during various user interactions, focusing on form validation, signup flow, and navigation.

Purpose:
The tests verify that the SignUpForm component provides correct user feedback, handles signup successfully, and navigates as expected when users interact with the form.
Mocking:

Firebase Functions: The Firebase functions (createUserWithEmailAndPassword, sendEmailVerification, setDoc) are mocked to isolate the component's behavior without real API calls.
Navigation: The useNavigate function from react-router-dom is mocked to validate navigation without actual redirection.
Tests Overview:

"should display validation error for weak password":
Type: Unit Test
Purpose: This unit test verifies that the component correctly handles password validation.
Behavior Tested: When a weak password is entered, it checks that the validation error message is displayed and createUserWithEmailAndPassword is not called.
"should handle successful signup":
Type: Unit Test and User Acceptance Test (UAT)
Purpose: The test is both a unit test for the signup logic and a user acceptance test to ensure a smooth user flow.
Behavior Tested: It simulates a successful signup flow, including submitting valid information, verifying if createUserWithEmailAndPassword, sendEmailVerification, and setDoc are called appropriately, and confirming the success message is displayed.
"navigates to the login page when 'Log In' is clicked":
Type: Unit Test and User Acceptance Test (UAT)
Purpose: This test ensures that the user can navigate to the login page.
Behavior Tested: It checks if clicking the "Log In" link triggers the navigation to the login page ('/').


loginForm.test.jsx
This file contains unit and user acceptance tests for the LoginForm component. The tests use React Testing Library and Jest to validate how the component behaves during different user interactions, specifically focusing on rendering, password visibility, and login functionality.

Purpose:
The tests verify that the LoginForm component renders correctly, handles password visibility, and manages login attempts (both successful and unsuccessful).
Mocking:

Firebase Functions: The signInWithEmailAndPassword function from Firebase is mocked to simulate login behavior without making real network requests.
Routing: renderWithRouter is used to wrap the component in a BrowserRouter, simulating a real browser environment for routing purposes.
Tests Overview:

"renders the login form":
Type: Unit Test
Purpose: Ensures that the LoginForm component renders properly with the email input, password input, and sign-in button present.
Behavior Tested: Verifies the initial rendering of the form to confirm that all expected elements are in place.
"allows user to toggle password visibility":
Type: Unit Test and User Acceptance Test (UAT)
Purpose: This test checks that users can toggle password visibility using the icon.
Behavior Tested:
Initially, the password should be hidden.
Clicking the toggle icon changes the type of the password input from "password" to "text" and vice versa.
As a UAT, it confirms that the component provides expected behavior for user convenience.
"displays error when login credentials are invalid":
Type: Unit Test and User Acceptance Test (UAT)
Purpose: Tests the login flow when incorrect credentials are provided.
Behavior Tested:
Mocks a rejected signInWithEmailAndPassword call, resulting in an error toast message.
As a UAT, it ensures that the user gets appropriate feedback when their login attempt fails.

