# TODO List for Dashboard Implementation

## Missing Features and Enhancements
1. **Persistent Frequency-Based Prioritization**:
   - Implement frequency-based prioritization for links.
   - Store frequency data and clear it after 7 days. (Not implemented yet.)

2. **Responsiveness**:
   - Add explicit messaging for unsupported screen sizes. (Not implemented yet.)

## Testing Plan
1. **Functional Testing**:
   - Verify that tabs switch correctly using both keyboard and mouse.
   - Ensure typeahead filtering works as expected (case-insensitive, matches anywhere in the title, description, or URL).
   - Test link navigation and launching via both keyboard and mouse.

2. **Visual Testing**:
   - Check that the dashboard adapts to both light and dark system themes.
   - Verify that long titles/descriptions are truncated and wrapped correctly.
   - Ensure hover effects and active tab highlights are visible and adapt to the system theme.

3. **Data Persistence Testing**:
   - Launch links multiple times and verify that frequently launched links are prioritized.
   - Confirm that frequency data is cleared after 7 days.

4. **Edge Case Testing**:
   - Test with special characters in titles, descriptions, and categories.

5. **Performance Testing**:
   - Verify that the dashboard loads instantly, even with a large number of links.
   - Ensure typeahead filtering remains responsive with a large dataset.
