Alerts is a feature that notifies user when some event occured according to data change

Key parts of alert features are: 1) Alert rule; 2) Contact Points; 3) Notification policies

By default alerts are sent via email but they are not limited to email only

##### Alert rule
Alert rule defines when alert will fire 

Alert rule creation process:
1. Section 2: Define query and condition when alert fired
2. Section 3: (optional) Select or create folder to organize rule
3. Section 3: (optional) Create label/s. This labels will be later used to whom is alert will be sent
4. Section 4: (optional) Select or create evaluation group. Evaluation groups are used to poll and fire (if alert rule condition is met) multiple alerts at same time.
5. Section 4: Set pending period (not required if evaluation group set). Pending period is how often condition will be checked
6. Section 5: (optional) Set to which contact points will alert be sent (if labels are not used)
7. Section 6: Define message structure. Message structure allows to use user defined labels `{{ $labels.app }}` and some macroses.

##### Contact Point
Contact Point is to whom and how alert will be sent

Contact Point creation consists of:
1. Name of contact point
2. Integration type
3. Recipient

For email notification select "Email" integration and write down email addresses

Via button "test" you could check if configuration is valid and data are sent

> [!NOTE]
> Docker image has disabled SMTP (email protocol) by default. To enable it, create container with `-e "GF_SMTP_ENABLED=true"`

![[Pasted image 20251019140640.png]]

