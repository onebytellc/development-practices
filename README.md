# Development Best Practices

Provides guidelines to developers for testing their application

# Web

## Form Validation

- Trimmed fields to avoid spaces acceptance. Acceptable only for passwords
- Numeric keyboard for number entry.
- Minimum and Maximum characters limit should be pre-defined in First name, Last name, password, confirm password.
- DOB format should be defined
- Email validation and verification
- Each required field should be completely validated and verified individually before moving to next one
- Hierarchy of validation on submit button: 
  - Field validation
  - Credentials check

## Responsive Design

- Screen should either be responsive or fixed-width
- When content needs to be centered vertically, fix the height of parent
- Widgets / Text should not overlap when screen size changes
- Define base font-size for the application before starting development

## Consistent Design Practices

- Designer should always provide a style guide and MUST use that style guide for all their screens
- Developers should agree on style guide before starting on a project and if time permits, create an implementation of style guide as well (http://ec2-52-90-113-143.compute-1.amazonaws.com:8000/style-guide)
- Implement a SCSS / LESS variable page and use those variables across CSS instead of hardcoding color, padding, radius, borders (https://bitbucket.org/onebytetech/servup-web/src/78365001c94cb3d9afaf0f1aaaffebe517af1804/client/modules/core/styles/variables.scss?at=master&fileviewer=file-view-default)
- Static (dummy) data must be taken out before the final build testing
- Placeholder images for user (and other resources) should be used across the application in case no image is provided from backend (or while the image is loading)
- Loaders should be used everywhere API response is required
- Timestamps should always be present with posts. Timestamp format should be pre-negotiated with web
- Tracking of “back” button should be pre-decided for all the views. On completion of signup and similar forms with multiple screens, back button should take the user to starting step instead of the last step
- URL Schemes for API’s and Frontend
- URL should always be lisp-case (or kebab-case)

## Unique email

- All URLs and their updates should be sent to qaonebyte@gmail.com with the subject “Project Name :/version”

# API's

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

## Unique email

- All builds and their updates should be sent to qaonebyte@gmail.com with the subject “Project Name : iOS / Android / React : version”
