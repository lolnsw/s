SRE Mission
Team mission and objectives:
Change implementation/oversight
Incidents response and resolution
Own post-mortems
Own monitoring for tech and functional products
Reduce/Eliminate Toil via automation
All above missions apply to environments used by customers (P for Dynamo customers, or D-P for devs customers - eks, logging, monitoring, tracing, networking, toolchain…)

Incidents and post mortems
The team picks up alerts 24/7 and aims to bring the service/product back online without/or little involvement from the development teams.
SRE owns and conducts blameless post mortems. Abbreviated post mortems should be documented shortly after each incident. Subsequently, to be enhanced/reviewed by SRE and Dev teams.
The communication/scribing/coordination of incidents are performed by mission control.

Monitoring:
SRE is the primary administrator of the monitoring dashboards/alerts but co-own this space with the development teams. When eventually mature, our monitoring should comprise of::
All functional and tech products monitoring to standardized cockpits
Continuously reduce signal-to-noise ratio, focus on customer impacts alerting. Reasonably fast burn alerting, without over alerting.
Alerts should all be actionable. With direct path to troubleshooting dashboards, logging dashboards in Kibana, with playbooks readily available.
Synthetic user for alerting and troubleshooting (ability to run on demand with parameters)
SLO agreed with application owners, alerting on those SLOs. Keep some fast burn alerts where it makes sense.

Notes:
Dev teams can (and should) still have their own monitoring dashboards, however no duplication of alerts
All new alerts need to be agreed by both SRE and dev teams, properly tested and only finally released to the environment.
SRE allowed to create branches for dashboards, grafana/prometheus configuration. Merge to be approved by the team owning those services in Core engineering.
SRE does not own the monitoring/logging/tracing platform. This should be a different core engineering team.







Change
SRE to be involved in every change from the start of the feature. 
SRE implements manual steps (if needed)
SRE confirms the release success with the development teams. (joint ownership)




Documentation and Training
On-call checklist:
Create and maintain on-call checklist (ex: know how to drain traffic, rolling back release, blocking/redirecting selected traffic, using monitoring alerting/dashboards, describe architecture, contacts, etc… non exhaustive list)
Create a defined boundaries of what the team supports
Help track progress of new joiners

Playbook vs runbooks
SRE owns and update playbooks and runbooks
Playbook:
Playbooks are high level steps to investigate and resolve issues. Contains none or very little manual steps
Every alert should have a runbook

Runbook:
Runbooks are a list of manual steps to conduct solve/investigate issues. They should not be long lived, and should either be tactical and eliminate by bug corrections, or automated if there is a need to keep the function. Once automated, the runbook should transitioned into a playbook (or included in an existing one)


Wheel of fortune rpg. on past/fictitious incident. One/2 team members brainstorm in front of the team to explain what thy would do (SRE best practice)


Eliminate toil
SRE identifies and eliminates toil (manual repetitive tasks that can be fully or mostly automated). The automation is to accelerate troubleshooting, restore procedures...




Organization
1 Core engineering squad
3 locations, minimum 6 in each location. Minimum to cover 24/7.
How the team will run after the initial phase:
The team is divided in engineers on call and not on call (rota based)
On-call means an engineer assigned to incidents detection/resolution during a shift (on-call is during the week/weekend/business hours, basically no distinction on the function, the same expectations for 24/7)
1 on-call engineer should, on average, tackle a maximum of 2 incidents per 12 hours (*Google recommendation). The on-call shift includes post mortems write up, change implementation, documentation updates. A minimum of 2 on-call engineers at any given time. On-call workload needs to be tracked to assess over/under utilization of on-call engineers, specially at the beginning.
Engineers not on call focus on automation and embedding.
How the team will run during the initial phase 
Same as above, except that the embedding may be owned by the same couple of engineers to ramp up knowledge.


On-call duties summary:


On-call
Not On-call
Response to alerts
X


Drive resolution
X
(*) Can be asked to help if needed
Post mortem
X


Change preparation


X
Change implementation/oversight
X
X
Monitoring improvement


X
Automation


X
Documentation
X (*) if times allows
X





Embedding:
SRE engineers will be embedded as follow:
Every new feature should include SRE resources
JIRA story raised to SRE for analysis of monitoring and resiliency matters related to this feature (joint ownership with dev team)
SRE must participate to the preparation of the change
SRE implements change and confirm success (joint ownership with Dev)
No constant/passive embedding, this has proved to be inefficient in the past. SRE should have stories to their name on the board and report back on dev stand-ups.
The embedded SREs are responsible to create/updates playbooks and runbooks.
The embedded SREs are responsible to pass on knowledge to the team for every new feature they are working on.
Embedding will be “static” in the early stage (same people embedding in the teams), This will be more flexible and rota based when there is confidence the replacements can operate at the same level. This rota does not have to be implemented for all products at the same time. The maturity of the team and the need for Dynamo will dictate which products can move to an embedded rota model.



Skillset
Need to embrace production support
Engineers - pick up the incident and aim at restoring service with no/minimal escalation.
Comfortable with working outside of office hours
Automation to be done in Python
AWS experience - eventual skills expected to be at the level of  AWS Sysops and Devops professional certification.


Roadmap overview



Incidents
Monitoring
Change
Documentation
Automation
Phase 1
1 sprint
Set-up on call rota
Response to all incidents
Own post-mortems


Embedding for new feature
Ensure validates all alerts have a corresponding playbooks. Write-up missing playbooks.




Phase 2
2 sprints


Standardize all dashboards for functional products to cockpits


On-call checklist review and update.
Toil review and definition
Phase 3
2 sprints


Standardize all dashboards for tech products to cockpits




Automation development starts
Phase 3+


Synthetic user
Agree on SLO with dev teams. 
Set-up error budget
Alert on SLO






Phase 3+




Features vs Stability conditioned on error credits






Notes:
For each above categories, reporting to be put in place to track success/failure of the program.
