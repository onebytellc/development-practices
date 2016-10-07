# Development Best Practices

Provides guidelines to developers for developing and testing applications. 

1. [Web](#web)
2. [API's](#apis)
3. [Mobile](#mobile-applications-android--ios--react)


*Note: All builds and their updates should be sent to qaonebyte@gmail.com with the subject “Project Name : iOS / Android / React : version”*

# Web

## Format and Validations

- Define validations for all form fields before starting the project and make sure you perform those validations on client-side unless otherwise specified
- Trim all text fields to avoid empty space acceptance. Empty spaces should only be acceptable in passwords
- Use number type field in HTML5 wherever you expect number only field
- Define maximum and minimum character limits for all form fields and put those validations on all the form fields
- Each required field should be completely validated and verified individually before moving to next one
- Format for dates should be discussed with the product owner and the same format should be used throughout

## Design

- Ensure that you understand the design and that the design can be implemented on the screen sizes we wish to support
- Define screen resolutions to support and bound the limits for different devices for responsive implementation (For example, mobile should be < 760, iPad should be >760 and < 1120) 
- Screen should either be responsive or fixed-width
- When content needs to be centered vertically, fix the height of parent
- Widgets / Text should not overlap when screen size changes
- Define base font-size for the application before starting development
- Designer should always provide a style guide and MUST use that style guide for all their screens
- Developers should agree on style guide before starting on a project and if time permits, create an implementation of style guide as well [Example Style Guide](http://ec2-52-90-113-143.compute-1.amazonaws.com:8000/style-guide)
- Implement a SCSS / LESS variable page and use those variables across CSS instead of hardcoding color, padding, radius, borders [Example Variable File](https://bitbucket.org/onebytetech/servup-web/src/78365001c94cb3d9afaf0f1aaaffebe517af1804/client/modules/core/styles/variables.scss?at=master&fileviewer=file-view-default)
- Static (dummy) data must be taken out before the final build testing
- Placeholder images for user (and other resources) should be used across the application in case no image is provided from backend (or while the image is loading)
- Loaders should be used everywhere API response is required
- Timestamps should always be present with posts. Timestamp format should be pre-negotiated with web
- Tracking of “back” button should be pre-decided for all the views. On completion of signup and similar forms with multiple screens, back button should take the user to starting step instead of the last step
- URL Schemes for API’s and Frontend
- URL should always be lisp-case (or kebab-case)

# Backend

## Code Structure

- Put controllers and models under `app/` directory
- Create a `config.json` with environment named keys in it `{ "development": {}, "production": {} }` or use configuration file based on environment names (`production.json`, `development.json`). All the environment specific items should be put in configurations and used from there. For example, DB credentials, App URL etc
- Always use [lodash](https://lodash.com) to work with arrays
- Always use (Moment](http://momentjs.com/) to work with dates
- Whenever working with MySQL, always create migrations to setup schema instead of writing queries locally to setup schema
- This yeoman generator sets up the application with all the above mentioned guidelines: https://www.npmjs.com/package/generator-maskers. Feel free to create a pull request to add stuff to it

## REST API's

- Always version the API's: `http://api.example.com/v1/users/3`
- Humans SHOULD be able to easily read and construct URLs
- Properly use the following methods:

|Method   |Description   |Idempotent   |
|---|---|---|
|GET   |Return current value of the object   |Yes   |
|POST   |Create a new object based on data provided   |No   |
|PUT   |Replace an object with provided object   |Yes   |
|PATCH   |Apply partial update to an object   |No   |
|Delete   |Delete the object   |Yes   |

- Get with `:id` should return a single object `http://api.example.com/v1/users/3`
- Get without `:id` should return an array of objects `http://api.example.com/v1/users`. Each object in array should contain an `:id` field that client can use to do further operations on the object
- Try to use nouns instead of verbs in the URL's. For example, use `POST /v1/users` instead of `POST http /v1/createUser`. __POST already means create, no need to specify create in the URL__.
- Use plurals in API's. `/v1/users instead of /v1/user`

## Request and Response Payload

- Use JSON for request and response payload
- Date format should always be ISO string (looks like this `{ "creationDate" : "2015-02-13T13:15Z" }` unless otherwise specified. 

# Mobile Applications (Android / IOS / React)

## Form validation

- Trimmed fields to avoid spaces acceptance. Acceptable only for passwords
- Numeric keyboard for number entry
- Minimum and Maximum characters limit should be predefined in First name, Last name, password, confirm password.
- DOB format should be defined
- Email validation and verification
- Each field should be completely validated and verified individually before moving to next one.
- Hierarchy of validation on submit button: 
  - Internet check
  - Field validation
  - Credentials check
  
## Internet checks 

- In case when WiFi is disconnected or Internet is off, app should not crash. Loader for API should stop after a certain timeout and the user should be notified

## Responsive design 

- Widgets / Text should not overlap when screen size changes

## Consistent design

- Consistent design across screens
- Static (dummy) data must be taken out before the final build testing
- Placeholder images should be used across the application in case no image is provided from backend (or while the image is loading)
- Loaders should be used everywhere API response is required
- Timestamps should always be present with posts. Timestamp format should be pre-negotiated with Android and iOS
- Scroll views should be implemented for all input fields. Keyboards should never cover the input field you are writing in
- Tracking of “back” button should be pre-decided for all the views. Signup and form stuff should be taken out of “back” button
- There should be a uniformity among design of the application on all platforms(Android/IOS/React)
- Avoid using application’s native font. Try using custom style-sheet on all platforms(Android/IOS/React). Coordinate with Design department

## Crash Analytics
