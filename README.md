# ITSM-PROJECT
**ABC Tech Company
Business Case:
ABC Tech is an mid-size organisation operation in IT-enabled businesssegment over a decade. On an average ABC Tech receives 22-25k IT incidents/tickets , which were handled to best practice ITIL frameworkwith incident management , problem management, change managementand configuration management processes. These ITIL practices attained matured process level and a recent audit confirmed that further improvement initiatives may not yield return of investment.ABC Tech management is looking for ways to improve the incident management process as recent customer survey results shows that incident management is rated as poor.

Machine Learning as way to improve ITSM processesABC Tech management recently attended Machine Learning conference on
ML for ITSM.Machine learning looks prospective to improve ITSM processes through prediction and automation. They came up with 4 key areas, where ML can

***Help ITSM process in ABC Tech***
1. Predicting High Priority Tickets: To predict priority 1 & 2 tickets, so
that they can take preventive measures or fix the problem before
it surfaces.
2. Forecast the incident volume in different fields , quarterly and
annual. So that they can be better prepared with resources and
technology planning.
3. Auto tag the tickets with right priorities and right departments so
that reassigning and related delay can be reduced.
4. Predict RFC (Request for change) and possible failure / misconfiguration of ITSM assets.

******Data needs to be queried from MYSQL data base (Read Only Access)**********

***Domin Analysis***

Whether is ticket is open or closed. All tickets are closed, so this attribute in inconsequential
It’s the no. of Hands offs between Resolution Agents before the issue gets resolved. Its could be 
an indicator for Priority. Generally High priority tickets should have less hand-offs to other 
agent. Re-assignments happen in following scenarios:
1) When the Agent at the time of creation assigns to wrong resolution team

2) When the issue require resolutions from multiple teams ( like software, infra teams) and 
there is no one single owner that could be established.

3) Some times issue is reassigned due to cursory or inadequate investigation.
Time stamp when the ticket was created. It may help in calculating time taken by the ticket to 
close and also in forecating volumes as index column.

Time Stamp when the ticket was reopened. Typically if the resolution agent closes/resolves the 
tickets without satisfaction of the user or the issue resurfaces, then the user re-opens the ticket 
and this time may be by increasing the priority, (ITIL doesn't recommend such behaviors). 
Reopen Time perse may not help but can be converted into binary yes/no to have the impact of 
Reopening on Priority

Time stamp when the ticket was resolved by the resolution agent. It may help in calculating 
time taken by the ticket to close. But will not help in forecating the volumes
Time stamp when the ticket was closed. Post resolution of the ticket, the user who was 
instrumental in creating the ticket. In cases where the used fails to close the ticket, the ticket 
gets automatically closed based on SLA and the intimation of closure goes to all the stake 
holders. 
Cursory look at the resolved and Closed time stamps show thay are almost some. Will 
be used for ticket WIP duration. Can be deleted post EDA.
The data Shows a list of CSVs

Its could be a code to capture the cause of incident. This information is updated by the ticket 
resolution agent. Since at the time of capture we the ticket creation agent will not know about 
the information, it cannot be a predictor. However if we assume that the Ticket Creation agent 
can see the list of related incidents at the time of creating a new ticket, the closure code can be 
of some value to assess the priority.

Count of number of interactions with customer before the ticket was resolved. In general sense, 
if the priority of the tickets is higher, the SLA will be stringent and the Resolution agent may try 
to have many calls to get as much information required for reproduction of issue etc. to resolve 
it. hence this could predict the priority

It seems for every interaction with the client on the incident a unique ID is generated. Since the 
count of interactions is already captured, we can delete the column.
Count of of same of similar incidents raised in past ( closed or WIP). Now many service 
management products have a feature to prompt this count at the time of capture of a new 
ticket. 

If the count is higher the agent interpret it as a repeat ticket or a ticket which was not 
resolved properly and raise the priority of the incident. This also means that Resolution team 
has just been doing works around and no serious effort to completely resolve that ticket or 
have failed to raise RFC ( if the scope for resolution was coming under RFC).There is a good 
chance that it might impact the priority.





