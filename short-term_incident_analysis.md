# Short-Term Incident Analysis

![](../images/workflow/Picture1-short-term.png)

###1. Check the Incidents Page
Voyance shows a prioritized list of incidents that have occurred in your environment over the past 2 weeks. In the default view, the highest priority incidents are shown at the top of the list. 

![](../images/workflow/Picture2-short-term.png)

You can also filter incidents by time (e.g., last week, last day, last 3 hours) and / or by locations within your environment. When filtering by location, only incidents occurring in the selected location, along with the number of clients in that location will be shown.

###2. Click on an Incident
Clicking into an incident shows incident details, which displays a summary of why an incident was flagged with a certain priority, by showing the deviation from a computed baseline.  For example, clicking on the "Clients could not connect due to RADIUS issues" incident shows that 1.5% of clients (41 out of 2772) experienced problems connecting to the RADIUS server between 9:15 am and 10:15 am on June 7th. You can also see a breakdown by device type. Voyance shows that 89% of the devices were mobile devices (phones or tablets).

![](../images/workflow/Picture3-short-term.png)

###3. Check Symptoms, Potential Root Cause(s) and Next Steps
Voyance automatically provides root-cause analysis information and next steps for each incident, along with the symptoms that manifested in clients at the time of the issue.

![](../images/workflow/Picture4-short-term.png)

In this case, a 100% of clients that tried to authenticate to the RADIUS servers were not authorized. We see that (as shown below) there are 2 RADIUS servers (Host-399962 Host-494981) that handled all of the requests for the unauthorized clients on SSID (ESSID-435713)

![](../images/workflow/Picture5-short-term.png)

###4, 5. Verify the symptoms
You can cross-check the symptoms by inspecting the raw data for one or more of the clients shown in the client list.

![](../images/workflow/Picture6-short-term.png)

Clicking on a client and then on the event timeline, we see the username of the client that failed to authenticate with the RADIUS server.

![](../images/workflow/Picture7-short-term.png)

Clicking on the charts and selecting the RADIUS tab shows that there were 6 EAP rejects at 9:32 AM, validating the symptom shown by Voyance.

![](../images/workflow/Picture8-short-term.png)

The above pieces of evidence suggest that the problem is isolated to the list of clients identified by Voyance and the symptom shown matches the raw data collected. You can take appropriate next steps (e.g., redoing 802.1x profiles) for these clients to resolve this issue.