# Technical Decisions

## 1. Single Self-Contained HTML File
- **Rationale**: To ensure instant loading and simplicity by avoiding external dependencies.
- **Implementation**: All HTML, CSS, and JavaScript are embedded within a single `dashboard.html` file.

## 2. Vanilla JavaScript and CSS
- **Rationale**: To minimize complexity and dependencies by avoiding external libraries or frameworks.
- **Implementation**: Leveraged plain JavaScript and CSS for all functionalities and styling.

## 3. Embedded Link Data
- **Rationale**: To allow easy editing of links without modifying the HTML structure.
- **Implementation**: Links are defined within a `<script>` tag with `type="text/plain"` and parsed at runtime.

## 4. Responsive Design
- **Rationale**: To ensure usability across various screen sizes, particularly desktop environments.
- **Implementation**: Utilized CSS Flexbox and media queries to adjust layout for smaller screens.

## 5. System Theme Adaptation
- **Rationale**: To provide a better user experience by matching the system's light or dark theme.
- **Implementation**: Used CSS `prefers-color-scheme` media query and CSS variables for theme-based styling.

## 6. Keyboard and Mouse Navigation
- **Rationale**: To enhance accessibility and user convenience.
- **Implementation**: Implemented arrow key navigation for tabs and typeahead filtering, with mouse interactions for tab selection and link activation. Resetting the search query also resets the active tab to the first tab.

## 7. Typeahead Filtering
- **Rationale**: To allow users to quickly search and access links.
- **Implementation**: Real-time filtering of links based on user input, with a floating result list displayed at the center of the screen. Matches are case-insensitive and search within the title, description, or URL.

## 8. Error Handling and Fallbacks
- **Rationale**: To ensure robustness in cases where system time retrieval fails or links have missing data.
- **Implementation**: Displayed a generic welcome message if system time is unavailable, and provided default values for missing link titles or descriptions. Links with missing descriptions are left blank, and empty tabs display a "No links available" message.

## 9. Frequency-Based Prioritization (Planned)
- **Rationale**: To prioritize frequently accessed links for improved user efficiency.
- **Implementation**: Not yet implemented; planned to store frequency data and reset it after 7 days.

## 11. Arrow Key Rendering in Key Indicator
- **Rationale**: To improve the visual representation of arrow key presses.
- **Implementation**: Arrow key presses are rendered as Unicode glyphs (←, →, ↑, ↓) in the key indicator. The indicator also supports multiple simultaneous key presses.

## 10. Documentation and User Instructions
- **Rationale**: To assist users in understanding dashboard functionalities.
- **Implementation**: Included a documentation footer with usage instructions, which hides upon user interaction.
