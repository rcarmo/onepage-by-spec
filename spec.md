# Self-Contained HTML Dashboard Specification

## **Overview**
The goal is to create a single, self-contained HTML file that serves as a lightweight dashboard for launching predefined links. The dashboard will feature typeahead filtering, keyboard and mouse navigation, and a simple, responsive design. It will rely on no external resources and will load instantly.

---

## **Core Features**
1. **Tabs for Categories**:
   - Links are grouped into categories, each represented by a horizontal tab.
   - Only one tab is visible at a time.
   - Tabs are navigable via:
     - Clicking a tab displays all links in that category, regardless of the search query.
     - Arrow keys for cycling between tabs (left/right).
     - Mouse clicks for direct selection.

2. **Typeahead Filtering**:
   - Filters links in real-time as the user types.
   - Matches anywhere within the title or description (case-insensitive).
   - Displays matching links in a floating list at the center of the screen, regardless of their category or tab, with a slight drop shadow.
   - Backspace refines the search, and Escape clears the search results and displays all links in the active tab.
   - Displays a message like "No matches found" if no results are available.

3. **Link Interaction**:
   - Links are displayed with a title and optional description in the floating list and inside tabs.
   - Links inside tabs are arranged horizontally and wrap around if necessary.
   - The code includes concise comments for clarity and maintainability.
   - Clicking or pressing "Enter" on a link in the floating list opens it in a new tab.
   - Links are navigable via:
     - Mouse hover and click for direct selection.
   - Long titles/descriptions are truncated with ellipses and wrapped if necessary.

4. **Greeting, Date, and Clocks**:
   - A top section dynamically displays a greeting (e.g., "Good morning") based on the system time.
   - The current date is shown in the "Month Day, Year" format (e.g., "February 20, 2025"), and is right-aligned.
   - A floating clock section is rendered under the date section.
   - The clocks display the current time in UTC, CET, Seattle, and India timezones.
   - The clocks are small, rendered inline under the date, and update continuously.
   - If the system time cannot be retrieved, a generic "Welcome" message is displayed without the date or clocks.
   - The clocks and date are always aligned to the right.
   - This fallback behavior is not implemented.
   - The clocks update every second to ensure accurate time display.

5. **System Theme Adaptation**:
   - The dashboard automatically adapts to the system's light or dark theme.
   - Hover effects, active tab highlights, and other visual elements adjust accordingly.
   - There is no manual toggle button or emoji for switching themes.

6. **Persistent Frequency-Based Prioritization**:
   - This feature is not implemented. Links are not prioritized based on frequency of use, and no frequency data is stored or cleared.
   - Links are defined in a `<script>` tag with `type="text/plain"` at the top of the HTML file for easy editing.

7. **Reset Functionality**:
   - A keyboard shortcut resets the dashboard to its default state:
     - Clears the current search.
     - Hides the floating list of matches.
     - Resets the active tab to the first tab.
     - This functionality is partially implemented. The `Escape` key clears the search but does not reset the active tab.
   - The documentation section at the bottom of the page animates out of sight after 10 seconds or when a key is pressed.
   - A keyboard indicator is displayed at the bottom left of the screen, showing the keys being pressed.
   - Special keys (e.g., "Enter", "Shift") are displayed in rectangular boxes, while regular keys are displayed in square boxes.
   - Arrow keys are displayed as Unicode glyphs (←, →, ↑, ↓) in the keyboard indicator.
   - Keys fade out a few seconds after being pressed.

---

## **Architecture**
- **Single HTML File**:
  - All content (HTML, CSS, and JavaScript) is embedded in a single file.
  - No external resources (e.g., fonts, libraries, or images) are used.

- **Static Configuration**:
  - Links and categories are defined in a simple text block within the HTML file for easy editing.
  - The text block is parsed into structured tabs and links during page load.
  - Each link belongs to exactly one category.
  - Links with missing titles display "Untitled."
  - Links with missing descriptions are left blank, and links with long titles or descriptions are truncated with ellipses.

- **Responsiveness**:
  - Optimized for desktop use with a responsive layout.
  - Assumes a minimum desktop screen size and does not adapt to very small screens.
  - No explicit messaging is displayed for unsupported screen sizes.

---

## **Data Handling**
1. **Link Configuration**:
   - Links are defined in a text block and grouped by category.
   - Each category corresponds to a tab.
   - Links are displayed in the order they are defined.

2. **Frequency Data**:
   - This feature is not implemented. No frequency data is stored or used for prioritization.

3. **Typeahead Filtering**:
   - Filters links in real-time based on the user's input.
   - Matches are case-insensitive and search anywhere within the title or description.

---

## **Error Handling**
1. **Invalid Links**:
   - Links with invalid or missing categories are omitted.
   - Links with invalid URLs are treated as valid and opened as-is.
   - Links with missing titles do not currently display "Untitled" as specified.

2. **Empty Tabs**:
   - Tabs with no links display a "No links available" message.

3. **System Time Retrieval**:
   - If the system time cannot be retrieved, a generic "Welcome" message is displayed without the date.

---

## **Testing Plan**
1. **Functional Testing**:
   - Verify that tabs switch correctly using both keyboard and mouse.
   - Ensure typeahead filtering works as expected (case-insensitive, matches anywhere in the text).
   - Test link navigation and launching via both keyboard and mouse.
   - Confirm that the reset functionality clears the search and resets to the first tab.

2. **Visual Testing**:
   - Check that the dashboard adapts to both light and dark system themes.
   - Verify that long titles/descriptions are truncated and wrapped correctly.
   - Ensure hover effects and active tab highlights are visible and adapt to the system theme.

3. **Data Persistence Testing**:
   - Launch links multiple times and verify that frequently launched links are prioritized.
   - Confirm that frequency data is cleared after 7 days.

4. **Edge Case Testing**:
   - Test with empty tabs and ensure the "No links available" message is displayed.
   - Test with links that have missing titles or descriptions.
   - Test with special characters in titles, descriptions, and categories.

5. **Performance Testing**:
   - Verify that the dashboard loads instantly, even with a large number of links.
   - Ensure typeahead filtering remains responsive with a large dataset.

---
