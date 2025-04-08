# cf-redirect-script
A Cloudflare redirect script that can be used to simulate a CF that guides the user to click on it and then redirect to the link they want the user to open

## Features

### HTML Structure
- The HTML structure is centered around a `div` with the class `cf - verification`, which contains all the verification elements.
- There is a hidden checkbox (`input[type="checkbox"]`) with the ID `humanCheck`. This checkbox is used to trigger the verification process when it is checked.
- A `div` with the class `cf - box` serves as a visual representation of the checkbox. When the hidden checkbox is checked, an orange tick appears inside this box.
- A `span` with the class `cf - text` displays the verification prompt text. Initially, it shows "Verify you are human", and after successful verification, it changes to "Success!".
- A `div` with the class `cf - logo - section` contains the Cloudflare logo (represented by a `div` with the class `cf - logo`) and the privacy and terms text (`span` with the class `cf - privacy`).

### CSS Styling
- **Global Styling**:
    - The `body` is centered both horizontally and vertically using `display: flex`, `justify - content: center`, and `align - items: center`. It has a light gray background color and uses a modern sans - serif font.
- **Verification Container**:
    - The `cf - verification` class has a white background, rounded corners, and a shadow to give it a card - like appearance. It uses `display: flex` to arrange its child elements horizontally.
- **Checkbox Styling**:
    - The `cf - box` class represents the visual checkbox. It has a border and rounded corners. When hovered, it changes the border color and adds a shadow for better interactivity.
    - The `cf - box.checked::after` pseudo - element is used to display the orange tick when the checkbox is checked. It uses the `clip - path` property to create the tick shape.
- **Text Styling**:
    - The `cf - text` class has a dark gray color and a specific font size and line height for readability.
- **Logo and Privacy Section**:
    - The `cf - logo - section` class arranges the logo and privacy text vertically. The logo (`cf - logo`) has a fixed width and height and uses `background - size: contain` to display the logo image properly. The privacy text (`cf - privacy`) is smaller and has a lighter gray color.

### JavaScript Functionality
- The `verifyHuman` function is called when the state of the `humanCheck` checkbox changes.
- When the checkbox is checked:
    - The `checked` class is added to the `cf - box` element, which triggers the appearance of the orange tick.
    - The text content of the `cf - text` element is changed to "Success!".
    - After a short delay (set by `setTimeout`), the user is redirected to the GitHub website.
- When the checkbox is unchecked:
    - The `checked` class is removed from the `cf - box` element, and the text content of the `cf - text` element is changed back to "Verify you are human".

## Usage
1. Replace the placeholder `data:image/png;base64,这里替换为你的标志base64代码` in the `style` attribute of the `cf - logo` element with the actual base64 - encoded image of the Cloudflare logo.
2. Open the HTML file in a web browser.
3. Check the checkbox to complete the verification. After successful verification, you will be redirected to GitHub.

## Compatibility
This code is compatible with modern web browsers that support HTML5, CSS3, and JavaScript. It is designed to be responsive and should work well on both desktop and mobile devices.
