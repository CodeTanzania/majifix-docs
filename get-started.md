# MajiFix

MajiFix was developed by the World Bank in Tanzania to solve the challenge of tracking problems in cities through citizen crowd sourcing.

MajiFix builds up on the movement of civic issue tracking by adopting since day zero the well known standard Open311 GeoReport v2.

MajiFix is completely open source. It is free to use and to adapt, or adopt by anyone.

## Our aim

With MajiFix, we aim to:

- Open city governments, by creating new communication channels with their citizens.
- Allow citizens to report problems they face in their daily lives, and empowering them to share existing problems.
- Support public service providers in solving each and every problem, while giving feedback to people about updates on the efforts to solve each problem.

## MajiFix components

MajiFix has different components. The following text provides brief description of each component.

### MajiFix API

MajiFix API is built on Node.JS. It is a RESTful API layer designed in support of reporting and tracking common public service (i.e. water) problems.

It is consists of a suite of node packages covering the business/domain logic (the part of a platform that encodes the real-world business rules that determine how data is created, displayed, stored and changed), built for performance and scale.

You can consider it as the data layer within a platform (including the data model). It is designed to be plugged into a templating layer, a mobile application or to be used with any other data consumer.

MajiFix API provides a starting point that's further advanced than a framework. It allows you to get a complete data layer up and running in minutes.

See source code [repository](https://github.com/CodeTanzania/open311-api).

### MajiFix management app

MajiFix management app is designed to help manages statistical information about system performance to official city managers.

See source code [repository](https://github.com/CodeTanzania/open311-mobile-manager).

### MajiFix citizen mobile app

MajiFix mobile app is used by citizens to help them instantly report problems to water utility company.

Work still continues in a private repository. A public repository will be available as soon as a stable release is published.

### MajiFix facebook messenger bot

MajiFix facebook messenger bot is designed to create more social engagement by allowing citizens to submit problems to the MajiFix platform through Facebook Messenger's interface without downloading the actual app.

See source code [repository](https://github.com/CodeTanzania/facebook-majifix-bot).

### MajiFix USSD

MajiFix USSD interface, specially relevant in places where not everyone owns a smartphone.

See source code _This is yet to be published_.

### MajiFix website

A public website, that publicly shows what is going on with the system.

See source code [repository](https://github.com/CodeTanzania/majifix.io).

## Our vision

MajiFix tries to achieve two main outcomes:

- Improving efficiency of public services, by providing relevant information to the relevant stakeholders,at the right time.
- Improving social accountability about public services, by providing public statistics about the performance of public services.
