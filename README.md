This is an implementation of the coding project at https://github.com/wheniwork/standards/blob/master/project.md utilizing Rails 5's API Only framework.


There is no front-end to this.  The following routes are what I've designed to meet the use cases described in the spec doc.

Assuming "actor" data is passed in using an HTTP header.  Will include more data here when I flesh that out more.

=====Employee Stuff======
GET /users/:id/shifts - get all shifts for employee
--{shift: SHIFT, manager: USER-SUMMARY}
GET /users/:id/summary/?start=DATE&end=DATE - get user work history for date range
--{summary: {start: DATE, end: DATE, hoursWorked: FLOAT}[]}
GET /users/:id/teammates/?start=DATE&end=DATE - returns other users that will be teammates with this user for date range
--{users: USER-SUMMARY}

=====Manager Stuff======
POST /shifts/ - create new shift
--{shift: SHIFT}
PUT /shifts/:shiftId - update a shift
--{employee_id: INT, start: DATE, end: DATE}
GET /shifts/?start=DATE&end=DATE - get shifts for date range
--{shifts:SHIFT[]}
GET /users/ - get info about all employees
--{USER-SUMMARY[]}
GET /users/:id/ - get info about employee
--{USER-SUMMARY}
