# Changelog

## Version 2.0 - December 30, 2025

### New Features ✨

#### 🎯 Trial Purpose Field
- Added "Trial Purpose / Opportunity Overview" field to capture what the customer is looking to test
- Displays in the form as a multi-line text area
- Shows in the kanban cards for quick reference (up to 2 lines)
- Appears in the customer detail view for comprehensive project understanding
- Helps team members quickly understand the opportunity when reviewing trials

#### ✓ Success Criteria Field
- Added "Success Criteria" field to define measurable goals for trial success
- Multi-line text area for detailed criteria definition
- Visible in customer detail view
- Enables better trial planning and alignment with customer expectations
- Examples of good success criteria:
  - "Increase bandwidth by 50% over 30-day period"
  - "Achieve 99% uptime"
  - "Reduce latency to under 10ms"
  - "Support 50+ concurrent users"

### Benefits 🚀

These new fields help:
- **Clarity**: Everyone on the team immediately understands what the customer wants
- **Alignment**: Clear success metrics ensure trial setup matches customer goals
- **Conversion**: Better understanding leads to more successful trials and higher conversion rates
- **Accountability**: Measurable criteria make it easy to determine if the trial was successful

### Bug Fixes 🐛

#### CSV Import Issues
- **Fixed**: CSV import now correctly handles multi-line text within quoted fields
- **Problem**: Previously only imported 3 projects when CSV contained 8 projects
- **Cause**: Parser was splitting by newlines before processing quotes, breaking multi-line fields
- **Solution**: Implemented proper RFC 4180 compliant CSV parser that processes character-by-character
- **Result**: All 8 projects from your CSV now import correctly with full addresses and notes intact

### Technical Changes 🔧

- Updated data model to include `trialPurpose` and `successCriteria` fields
- Modified form to include new fields in "Trial Overview" section
- Enhanced kanban cards to show trial purpose (when available)
- Updated customer detail view to display both new fields
- Fixed React loading issue by moving scripts to body
- **Fixed CSV import bug**: Now properly handles multi-line text within quoted fields (addresses, notes, etc.)
- Improved CSV parser to be RFC 4180 compliant
- All existing data remains compatible (new fields default to empty strings)

### Migration Notes 📝

- Existing projects will have empty values for these new fields
- You can edit any project to add trial purpose and success criteria
- No data loss - all existing fields remain unchanged
- Export/import functionality fully supports new fields

---

## Version 1.0 - Initial Release

- Kanban board with 6 status columns
- Customer view and list view
- Project management with equipment tracking
- Timeline tracking with status dates
- Contact management
- Notes and next steps
- Export/import functionality
