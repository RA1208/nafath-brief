Version: NAFATH-V2
Track: AI
# Keeping a 5G Service Running Under Stress
## Overview
A reliable 5G service for emergency responders depends on several IT disciplines working together. Software engineering helps prevent duplicate actions when requests are retried after communication failures. Artificial intelligence can forecast network congestion, but its predictions must be evaluated carefully to avoid models that perform well only on training data. Mobile applications should remain useful during connectivity loss and synchronize information safely when service returns. Network slicing can provide tailored connectivity for emergency traffic, although it cannot eliminate every failure or security risk. Cybersecurity teams need structured incident response procedures to detect attacks, contain their impact, and restore operations. Finally, well-designed data models help managers monitor service usage by region and day. Together, these disciplines support informed decisions, operational continuity, and safer emergency communications.
## Software
HTTP safe methods, such as GET and HEAD, are used to retrieve information without requesting changes. OPTIONS and TRACE are also safe methods. Idempotent methods include GET, HEAD, PUT, DELETE,OPTIONS, and TRACE. This means repeating the same request has the same intended effect as sending it once. This is important in 5G services because connections may fail. Safe automatic retries help prevent
unwanted duplicate actions.
Resource: RFC 9110: HTTP Semantics - https://www.rfc-editor.org/rfc/rfc9110.html
## AI
Overfitting happens when an AI model learns the training data too closely and performs poorly on new data. For example, a model predicting 5G network congestion may work well during training but fail during real emergencies. Cross-validation helps detect this problem by dividing data into different groups. The model is trained on some groups and tested on others. This helps us understand whether the model can make reliable predictions on new data.
Resource: Scikit-learn: Cross-validation: evaluating estimator performance - https://scikit-learn.org/stable/modules/cross_validation.html
## Mobile
Mobile applications used by emergency responders should continue working when the internet connection is lost. Important information can be stored locally on the devices users can access it offline. When the connection returns, the app should synchronize the saved information with the server. It should also handle possible conflicts and avoid sending duplicate requests. This helps emergency responders continue their work during network interruptions.
Resource: Android Developers: Build an offline-first app - https://developer.android.com/topic/architecture/data-layer/offline-first
## Networking
5G network slicing allows operators to create separate logical networks using shared infrastructure. Each network slice can be designed for specific needs, such as speed, reliability, or low delay. For emergency responders, a dedicated network slice can provide suitable resources and priority for important communications. This can help emergency teams communicate during busy periods. However, network slicing alone cannot guarantee that the service will never fail. Good planning, monitoring, and security are still necessary.
Resource: 3GPP: Network Slicing - https://www.3gpp.org/technologies/slicing
## Cybersecurity
Cybersecurity incident response includes four main stages: preparation, detection and analysis, containment and recovery, and lessons learned. If an emergency 5G service is attacked, the security team should first identify the problem and understand its impact. Then, they should isolate affected systems, remove the threat, and restore services safely. After the incident, the team should review what happened and improve security measures to prevent similar attacks.
Resource: NIST SP 800-61 Rev. 2: Computer Security Incident Handling Guide - https://csrc.nist.gov/pubs/sp/800/61/r2/final
## Data
A star schema organizes data using one central fact table connected to dimension tables, such as date and region.
It is simple to understand and useful for creating reports. A snowflake schema divides dimension tables into smaller related tables. This reduces repeated data but makes queries more complex. For a 5G service, a star schema is a good choice for reporting daily network usage by region because it makes data analysis and reporting easier.
Resource: Microsoft Learn: Understand star schema - https://learn.microsoft.com/en-us/power-bi/guidance/star-schema
## Misconception in My Track
## Open Question
