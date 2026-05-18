# Science Olympiad Feedback Portal — Setup Guide

This guide explains how to connect the website to Google Forms and Google Sheets, and how the backend system works.

---

## System Flow

```
Website → Google Form → Google Sheets → Yearly Analysis → Program Improvements Page
```

1. **Website** — Students and parents access the portal and submit feedback.
2. **Google Form** — Collects responses and sends them to a linked spreadsheet.
3. **Google Sheets** — Stores each submission as a row (timestamp + answers).
4. **Yearly Analysis** — Leaders analyze the spreadsheet at the end of each season.
5. **Program Improvements Page** — Summaries are posted to show that feedback led to changes.

---

## Step 1: Create the Student Feedback Form

1. Go to [Google Forms](https://forms.google.com) and create a new form.
2. Title it: **Science Olympiad Student Feedback**
3. Add these questions (enable “Collect email addresses” only if you want; for anonymity, leave it off):

### Basic Information

| Question | Type | Options |
|----------|------|---------|
| What grade are you in? | Dropdown | 6, 7, 8 (or your grades) |
| How many years have you participated in Science Olympiad? | Dropdown | 1, 2, 3, 4 or more |
| Which event(s) did you compete in? | Checkboxes or Paragraph | List your events or allow free text |

### Rating Questions (1–5 scale)

Use **Linear scale** from 1 (Strongly Disagree) to 5 (Strongly Agree):

- The team selection process was clear and fair.
- Event assignments were communicated clearly.
- The progress check-in system helped me stay organized.
- Communication about practices and competitions was clear.
- Invitational competition schedules were well organized.
- I understood what was expected of me during the season.

### Open Response Questions

Use **Paragraph** type:

- What part of the program structure helped you the most?
- What is one thing about the program organization that could be improved?
- Do you have suggestions for improving communication, scheduling, or event assignments?
- Is there anything else you would like the leadership team to know?

4. In the form **Settings**, enable “Limit to 1 response” only if you want to restrict by signed-in accounts; for anonymity, leave it off.
5. Go to **Responses** → **Link to Sheets** → Create a new spreadsheet or select an existing one.
6. Copy the **Form ID** from the URL:  
   `https://docs.google.com/forms/d/e/**FORM_ID**/viewform`

---

## Step 2: Create the Parent Feedback Form

1. Create another Google Form: **Science Olympiad Parent Feedback**
2. Add these questions:

### Rating Questions (1–5 scale)

- Communication from the leadership team was clear.
- Competition and invitational schedules were well organized.
- Event assignments for students and parent coaches were clear.
- The program structure helped my child stay organized.
- Overall, the Science Olympiad program was well managed.

### Open Response Questions

- What aspects of the program’s organization worked well?
- What improvements would you suggest for next season?
- Do you have suggestions for improving communication with parents?
- Would you recommend this program to other families? Why or why not?

3. Link this form to the **same Google Sheets** as the Student form (add a new sheet tab).
4. Copy the **Form ID** from the form URL.

---

## Step 3: Connect the Website to the Forms

1. Open `student-feedback.html` and replace `YOUR_STUDENT_FORM_ID` in the iframe `src` with your Student form ID:
   ```html
   <iframe src="https://docs.google.com/forms/d/e/YOUR_STUDENT_FORM_ID/viewform?embedded=true" ...>
   ```
2. Open `parent-feedback.html` and replace `YOUR_PARENT_FORM_ID` with your Parent form ID.
3. Test both pages in a browser to confirm the forms load.

---

## Step 4: How the Backend Works

### Google Forms → Google Sheets

- Every form submission creates a new row in the linked spreadsheet.
- Each row includes a timestamp and the answers to every question.
- Responses appear automatically; no coding is required.

### Organizing Responses by Year

Two common approaches:

**Option A: Separate sheet tabs per season**

- In Google Sheets: **Add sheet** (e.g., “2024-25 Student”, “2024-25 Parent”).
- Before each season, duplicate the form and point it at the new tab, or:
- Use one form and at the end of the season, copy responses into a “2024-25 Archive” sheet and clear the main sheet.

**Option B: Single sheet with season filter**

- Add a “Season” or “Year” question to each form (Dropdown: 2024-25, 2025-26, etc.).
- Keep all responses in one sheet and filter by that column when analyzing.

---

## Step 5: Yearly Analysis

At the end of each season:

1. Open the spreadsheet and review the responses for that season.
2. **Rating questions**: Calculate the average for each 1–5 question.
3. **Open response questions**: Read through responses and list common themes and suggestions.
4. Note what changes were made in response (or will be made next season).
5. Update `program-improvements.html` with a new season card (see the structure of the existing 2024-25 and 2023-24 examples).
6. Keep the page focused on summaries and actions, not raw data.

---

## Reusing the System Each Year

- Add a new season section to the Program Improvements page.
- Optionally add a “Season” question to forms and filter by year in the spreadsheet.
- Or create new sheet tabs for each year and point forms to the new tab when you duplicate them.
- The website pages do not need structural changes; only the Program Improvements content and form links (if you create new forms) need updates.

---

## Customization

- **Colors**: Edit the `:root` variables in `styles.css` (e.g., `--primary`, `--accent`) to match your school colors.
- **Forms**: Add or remove questions in Google Forms as needed; no code changes are required.
- **Hosting**: Upload the HTML and CSS files to any static hosting (e.g., GitHub Pages, Netlify, school server) or serve them locally.
