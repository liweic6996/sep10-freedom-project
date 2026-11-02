# Content
Topic: **Public Transportation**

## Overview/Introduction/Context
* The general consensus of the public usually rounds to one concept: making public transit faster. 
  * For as long as the system has existed, our public transit networks have suffered from chronic delays, miscommunications, service disruptions, confusion, and incidents. This issue is one of the most enduring New York City has ever seen, and yet despite our efforts, it continues to persist. We must act to push back against this.

## Part A: existing technology

##### Software
* Communications-Based Train Control (CBTC)
  * The Communications-Based Train Control (CBTC) system is a combined software-hardware operating assistant that serves as what is essentially a digitized air traffic control system for trains. This system, designed to replace 1930s-era signalling technology helps reduce collisions, runs more frequent service, and operates trains autonomously.
    * CBTC is primarily used for trains to communicate back to the RCC [Rail Control Center] their precise location and speed. While not widely implemented across most lines and being completely incompatible with legacy SMEE [Straight-Air Motor Car Electric-Pneumatic Emergency, or Self-Lapping Mechanical Electrical Equipment] rolling stock, CBTC is widely relied on to run service in various fields.

 [See the diagram here.](https://lh3.google.com/u/0/d/1mwzlZyXGlDbDD3rha-aPYAxBqzHxs5om=w1920-h946-iv1?auditContext=forDisplay) [Find the source here.](https://www.consystec.com/nycsra2022/web/spinstance.htm?id=PT01-02) This diagram depicts the various operational sectors of typical Communications-Based Train Control infrastructure. We begin with the primary diagram markers (receivers / transmitters).
   * Rail Control Center (RCC): Green, Transit Management Center
     * The dispatch office that manages each route
   * UWB Radio Wayside Unit: Orange, UWB Transponder / Zone Controller
     * Trackside computers & wireless radios mounted to tunnel walls
   * Onboard Equipment: Blue, CBTC Components / UWB Radio
     * Computers / radios riding within the train cars
    
 Within the diagram, we can see there are various labels transferring data between each marker. 
   * `train movement restriction_ud`: Safety / speed limits, restrictions, regulations
   * `train operations data_ud`: Schedule, routing directions, operating mode shifts
   * `vehicle location and motion_ud`: Live status report (exact location & speed)
   * `UWB position request_ud`: Tracking ping system. A trackside beacon sends a signal to the train asking for its phyical distance.
   * `UWB position_ud`: The exact response coordinates sent back from the train, calculating its exact location to a few inches via ultra-wideband radio waves

Note in this situation, `_ud` means user-defined, customized data paths built for transit network architecture operating under the Metropolitan Transportation Authority.
   * This system combined runs dynamic braking zones, which creates a safety net for trains (or a moving block) to space out operational equipment evenly.
     * This also works to prevent collisions by automatically applying the brakes of the following train if the train ahead is slowing down or is not moving, leading to a distance loss.
   * In addition, this system operates trains via ATO (Automated Train Operation), handling the movement of the train on its own, which increases efficiency and reduces operational mistakes.
     * Human presence is still required in the cab to start the train, operate the doors, and manually apply the brakes in the event of an emergency.
    
To Note: The NYCS / NYCTA's CBTC is likely proprietary software, allowing for more flexible expansions via contractors

##### Hardware
###### Station Features
Station features range widely from basic needs, such as help point intercoms, to countdown clocks (CDCs) and WiFi/cellular receptions and capabilities.

* Help Points
  * [See the works of the new AP 7161 HP configurations here.](https://www.boycetechnologies.com/wp-content/uploads/2015/05/NYCTransit_HelpPoint_CaseStudy.pdf)

Help points are crucial hardware infrastructure within the New York City Subway. These pieces of hardware help commuters call emergency services in a situation where their phone is not available, as well as to connect commuters to station employees for information, such as directions. However, over time during their initial rollout, they faced various issues, such as vandalization and equipment deterioration. Motorola's AP 7161 upgrades resolved these various issues to ensure passenger safety and security.

* Voice Quality Issues
  * Ambient noise in subway stations often drowns out a person in need of immediate assistance, especially with degraded microphone technologies. A degraded help point could result in the death of a person; Motorola solved this with advanced VoIP technology.
* Maintenance & Condition Issues
  * The harsh conditions of the underground subway system often meant legacy help points took a beating and required heavy maintenance. Motorola resolved this issue by adding industrial-rated radios designed to withstand extreme temperatures and climates. In addition, remote centralized monitoring was retrofitted to enable troubleshooting from data centers.
 
By reinforcing Help Points, the New York City Subway regained one of its most critical pieces of hardware, designed to save lives while standing out for passenger safety.

* Station Arrival Information
  * [See the works of Adam Fisher-Cox's CDC simplification here.](https://www.adamfishercox.com/portfolio/mta-platform-screens/)

Countdown Clocks are crucial hardware infrastructure within the New York City Subway. These pieces of hardware help commuters identify with absolute confidence the remaining wait time until the train they need arrives. However, legacy software quickly became outdated for 2025-level operations, with cluttered design and inefficient cycling. Even this process was made efficient using a combination of new design tactics:

* Wait Time Issues
  * When one train left, legacy software would cycle through every single upcoming arrival for the next five trains. This made it difficult to identify which train served as a better alternative, as the long wait time between each cycle led to trains leaving before they could be considered properly.
    * Fisher-Cox's newer design cycles the next train more frequently, allowing for a final choice for commuters to save time.
* Accessibility
  * Legacy arrival software displayed only the terminal, making it redundant for passengers towards the end of the route.
    * Fisher-Cox's newer design cycles indicate the precise direction and destination of every train, allowing commuters to determine which train is theirs with more precision.
* Alerts
  * Legacy software completely blocked out all arrivals to cycle an extremely slow, often redundant alert twice, causing passengers to miss their train. In addition, this software did not display alternatives for passengers during scheduled service disruptions.
    * Fisher-Cox's newer design pairs the service alert on the bottom, with arrivals on the top to enable dynamic flow without having to wait for a service alert to cycle through. In addition, this newer design also introduced alternative directions onto countdown clocks positioned on platforms where service is temporarily unavailable.
   
By reinforcing the countdown clock system, the New York City Subway made quick arrivals more accessible to all.

## Part B: possible future technology
* Advanced Communications-Based Train Control (ACBTC)
  * While current CBTC is widely effective for maintaining efficient, reliable service, it can accommodate a service reduction, but cannot work around one. Once an incident as simple as track litter occurs, the entire CBTC system becomes practically useless, as it cannot operate trains that cannot move. As such, disruptions like these often lead to partial suspensions, creating a massive, daily logistical headache for commuters who simply want to get to their destination on time. As such, I promise a newer, state-of-the-art Advanced Communications-Based Train Control system. This new ACBTC system would be much more intelligent and route around service disruptions to prevent complete loss of service.
As we know, during partial suspensions, an entire portion of a branch gets hit with an outage / loss of service. During sudden disruptions like these, there is little to no way to work around such a disruption without running late immediately or being crammed into a crowded alternative alongside hundreds other commuters thinking the same as you. However, ACBTC would bypass service loss entirely.
* ACBTC would utilize the New York City Subway's complex network of track switches to immediately route around a service disruption.
  * Say, an unauthorized person is caught trying to breach the northbound tracks at Canal St (Nassau). [See the track map here.](https://lh3.google.com/u/0/d/1ByfM_Xzz5Iu5X2bpCxVdHYmgFqBd6cfo=w1920-h946-iv2?auditContext=prefetch)
    * ACBTC would immediately route northbound (J/Z) trains through the abandoned eastern platforms, on track four, bypassing Bowery and merging back to the mainline at Delancey-Essex Sts. This system would quickly calculate this as the most efficient route with minimal disruption to service while NYPD conducts an investigation on track two.
   
* Now, let's say this happens somewhere where there is no abandoned side track, such as [6 Av-Bryant Park](https://lh3.google.com/u/0/d/13KTBua2Nn7O26vSUyR9XEAoDIsVN7svD=w1920-h946-iv1?auditContext=prefetch) heading northbound just past Herald Square. An NYPD investigation is being conducted on the northbound track south of 42 St-Bryant Park.
  * ACBTC would immediately utilize the disused track switches north of 34 St to wrong rail trains to the southbound express track, pushing them through and back via the following switch, holding trains briefly at Bryant Park to allow for this to happen.
    * If this system were to become overwhelmed, trains would instead route via the local track, rather than switching back to the express for Bryant Park, only switching back to the express when necessary. This would reduce the strain put in that particular section, lowering switch wear.
   
Another primary issue is navigational signage. Because most rolling stock databases are fixed and do not allow manual setup, they are confined to existing programs. Therefore, in the event of a reroute, there may be no program that displays the temporary service pattern being taken, leading to mass confusion from passengers onboard.

  * My solution to this problem would be to allow manual modifications of the program from the conductor's position, enabled by employee identification numbers, to provide accurate information even during an unprecedented service disruption.
    * To combat unruly passengers breaching the cab to exploit this system and use it against itself to cause confusion (which is an actual problem), this feature would be disabled behind an employee identification number lock. Therefore, even if an employee gives out their identification badge, the unauthorized entry would easily be traced back to said employee.
      * The goal of this new software addition would be to notify passengers visually of a change in route, especially as the sound via the passenger announcement system can often be drained out by degraded speakers or noisy background.
   
ACBTC would be an extremely efficient, streamlined automated system designed to keep the system moving, even in situations where disruptions happen. I have further plans for expansion of capabilities of this technology, though this functionality is the primary purpose.
