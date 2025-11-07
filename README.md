# airtable_project_tracker
🔗 [View the live Airtable base (read-only)]https://airtable.com/app2FaT2iXXetmx8n/shrd0PEKubTmNTzzi

# Airtable Project Tracker with Automated Status and Activity Score

This Airtable base was designed to help manage team reporting and management for each month. It includes calculated fields that assign an **Activity Score** based on meeting attendance and project submissions. Minimum score is assigned when members attend at least 2 out of 3 total meetings. Excused absences count. Members can also attain a minimum score if working asychronously, in which they submit a project while in contact with leaders. Minimum score = 50. A **Current Status** field automatically categorizes each member as "✅ Active (Met minimum)" or “⚠️ Inactive (Below minimum)” for quick visual monitoring.

### Features
- **Automated Scoring:** Uses a weighted formula combining attendance and project submission for the month.
- **Dynamic Status Tags:** Logic-based field updates in real time.
- **Team Dashboard:** Interface displays team statistics, such as member breakdown, project topics, etc.
- **Automations:** Three automations to flag inactivity "Follow-up Monitor ✅", badge status "Presentation Badger 🦡", and graduation certificate status "Grad Certificate Tracker 🎓". Automations list members in the relevant table for leaders to follow up.
  
- **Formula Example:**
IF(
  IS_SAME(
    DATETIME_FORMAT({Current Session}, 'YYYY-MM'),
    DATETIME_FORMAT(TODAY(), 'YYYY-MM')
  ),
  (
    IF(({Meetings Attended - Current Session} + {Excused Meetings - Current Session}) >= 2, 50, 0)
    +
    IF({# Presentations Submitted} > 0, 50, 0)
  ),
  0
)
- **Use Case:** Improves visibility into member activity and management tasks for leaders.

### Skills Demonstrated
- Spreadsheet logic and formula creation  
- Data visualization and dashboard design  
- Process optimization and tracking  
- Collaboration workflows using Airtable
- Creating automations to minimize manual tracking
