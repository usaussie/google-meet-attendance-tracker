# Google Meet Attendance Tracker

### OVERVIEW

Want to know which people you most do Google Meets with? How about which meetings have the most people, or how your meeting attendance changes over time?

Premise: 
Host a Google Meet -> Google sends you a CSV after with attendee details -> Appscript processes your attendee CSVs into a central Google sheet -> Now you can report/slice/dice/dashboard to your heart's content.


### ASSUMPTIONS:
 - The CSV filename format used by Google (as of October 9th) is: "YYYY-MM-DD HH-MM Name of Meeting.csv"
 - If the name format changes, the script may generate unexpected data for some of the derived columns (meeting name and date)
 
### INSTRUCTIONS
 - Create a new project in google appscript (script.google.com)
 - Copy the Code.gs file contents into appscript, update the variables at the top (link to your google sheet, tab name, folder for CSVs)
 - Run the set_sheet_headers() function once, which will prompt for permissions and set the sheet column headers
 - Accept the permissions (asking for access for your script to read/write to google drive etc)
 - Every time you get a CSV after a google meet session, move it into your Google Drive pending folder
 - Run the process_all_pending_csv_files() function (once, or set a trigger)
 - Look in your google sheet as the function is running, and you should see results being inserted

### RECOMMENDATION:
 - If you run this using a triggered schedule, then all you need to do, is move any CSVs into your pending folder, and they'll automatically get aggregated.
 - This is then easy to add as a source to a Data Studio Dashboard. And...if you use the email/row permissions, people would only see their attendance and no one elses :-)
