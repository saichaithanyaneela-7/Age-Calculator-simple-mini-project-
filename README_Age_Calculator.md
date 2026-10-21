# Age Calculator

A simple, browser-based **Age Calculator** built with HTML and JavaScript. Enter a birthdate and click **Calculate Age** to find your age in years.

## Features

- Accepts a birthdate using the browser's date picker.
- Calculates age in completed years.
- Checks whether the birthday has occurred yet this year.
- Displays a message if no birthdate is entered.
- Runs directly in a web browser; no installation or external libraries are required.

## Technologies Used

- **HTML** — page structure, date input, button, and result area.
- **JavaScript** — age calculation and result display.

## Project Structure

```text
age-calculator/
└── index.html
```

The project can be kept in a single `index.html` file because the JavaScript is embedded in the HTML document.

## How to Run

1. Save the supplied code in a file named `index.html`.
2. Open the file in a modern web browser (for example, Chrome, Edge, or Firefox).
3. Select your birthdate.
4. Click **Calculate Age**.
5. Read the result displayed below the button.

## How It Works

1. JavaScript reads the selected date from the `birthdate` input.
2. If no date is selected, the page displays: `Please enter a valid birthdate.`
3. The program gets the birth year and the current year, then subtracts them.
4. It compares the current month and day with the birth month and day. If the birthday has not happened yet this year, it subtracts one from the calculated age.
5. The result is displayed on the page, such as `You are 21 years old.`

## Example

**Input:** A birthdate that means the person is 21 years old today.

**Output:**
```text
You are 21 years old.
```

The displayed age depends on the birthdate entered and the current date.

## Limitations

- The code reports age in whole years only; it does not show months or days.
- It checks for an empty date, but does not explicitly reject future birthdates.
- The current version has basic HTML only and no custom CSS styling.

## Possible Improvements

- Add CSS to make the page more attractive and responsive.
- Validate and reject future birthdates.
- Display age in years, months, and days.
- Add a reset button and improve accessibility.

## License

This project is provided for learning and educational use. Add a license file if you plan to distribute it under specific terms.
