# aFRR Glossary

## Aggregate Baseline

A Baseline is the planned power output of a resource over a certain period of time and represents the behavior of the pool of resources without an activation by the TSO.

## Aggregate Measurement

The aggregate measurement is the actual measured power output of all connected resources together over a certain period of time, calculated and reported by the BSP.

## Automatic Frequency Restoration Reserve (aFRR)

*(also called R2 and réserve secondaire in France)*

aFRR is part of the frequency ancillary services. It acts after the FCR (30 seconds to 5 minutes later and up to 15 minutes) and restores system frequency at a country level.

## Balance Responsible Party (BRP)

A market party, or the representative chosen by a market party, that is responsible for its imbalances.

## Bid

In Bidding app, we send energy bids to the national TSOs of France (RTE) and the Netherlands (Tennet).  
aFRR capacity and energy bids target time steps of 15 minutes.

## Crowd Balancing Platform (CBP)

The CBP is a blockchain-based system to share relevant information between the participating parties in a transaction – such as TSOs, DSOs, Aggregators, and data providers – in a trusted and secure way. The CBP facilitates the standardized registration, bidding, and activation of flexibility transactions from aggregators of distributed energy resources.

## European Network of Transmission System Operators for Electricity (ENTSO-E)

ENTSO-E, the European Network of Transmission System Operators, represents 39 electricity transmission system operators (TSOs) from 35 countries across Europe. ENTSO-E promotes closer cooperation across Europe’s TSOs to support the implementation of EU energy policy and achieve Europe’s energy and climate policy objectives, which are changing the very nature of the power system.

## Energy Identification Code (EIC)

The Energy Identification Code or EIC is a 16-character identifier (code) used in Europe to uniquely identify market participants and energy resources (entities and objects) related to the electricity and gas sector.

## Frequency Ancillary Services

*(also called services système fréquence in France)*

Frequency control refers to the need to ensure that the grid frequency stays within a specific range of the nominal frequency.

A mismatch between electricity generation and demand causes variations in frequency (for example, if there is a power plant outage), so control services are required to bring the frequency back to its nominal value and ensure it does not vary out of range.

In Europe, there are 3 mechanisms within frequency ancillary services: aFRR, FCR, and RR.

## Frequency Containment Reserve (FCR)

*(also called R1 and réserve primaire in France)*

FCR is part of the frequency ancillary services. It acts first, at the European level, and contains the frequency deviation in less than 30 seconds.

## Full Activation Time (FAT)

The Full Activation Time (FAT) defines the maximum allowed duration for the full activation or deactivation of a standard aFRR energy bid. The compliance of each BSP with the FAT requirement is checked during the prequalification process and is later translated into local monitoring rules.

## Imbalance Settlement Period (ISP)

ISP corresponds to the time granularity at which imbalances are calculated and settled. This interval reflects the time granularity at which BRPs are required to be balanced.

In the past, ISP was also known as Programme Time Unit (PTU). The ISP is fixed at 15 minutes for aFRR.

## Load Frequency Control

The system used by TenneT to enforce the national balance and send the delta setpoints.

## PICASSO

The PICASSO project (Platform for the International Coordination of Automated Frequency Restoration and Stable System Operation), launched by 26 European TSOs, is a platform for exchange of automatic frequency restoration reserves.

The French TOPNIVEAU platform and the Dutch Tennet platform will be connected to PICASSO.

## Regulation Entity

*(also called entité de régulation - EDR - in France)*

This is the main entity handled by the Bidding app. It groups the regulation assets (like batteries) which are treated together in the Bidding app.

In the Bidding app, these entities are retrieved from Everest. In Everest, this entity is called a *control unit* or *demand response entity*.

## Replacement Reserve

*(also called R3 and réserve tertiaire in France)*

Replacement reserve is part of the frequency ancillary services. Replacement reserve is activated manually and restores power in the long term.

## TOPNIVEAU

RTE platform where aFRR energy bids can be sent.

## Tile

Block allowing monitoring of real-time asset status.

## Telemetry Point

These are data series reported by the box installed on a site. For example, the measurement of a battery's power is reported every X seconds to a dedicated telemetry point.