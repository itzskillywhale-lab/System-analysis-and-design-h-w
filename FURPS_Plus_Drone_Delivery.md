# FURPS+ Requirements Analysis: Autonomous Hospital Drug Delivery Drone

## 1. System Overview

An autonomous hospital drug delivery drone is an unmanned aerial vehicle (UAV) designed to transport medicines, vaccines, blood products, and other approved medical supplies between hospitals, pharmacies, laboratories, and healthcare facilities.

The **FURPS+ model** organizes requirements into functional capabilities, quality attributes, and additional constraints.

- **F — Functionality**
- **U — Usability**
- **R — Reliability**
- **P — Performance**
- **S — Supportability**
- **+ — Additional constraints**, including safety, security, hardware, interfaces, and regulatory requirements.

> **Important:** The numerical values below are proposed coursework targets, not validated engineering specifications or legal thresholds. They must be confirmed through risk analysis, stakeholder review, testing, and regulatory assessment.

## 2. Functional Requirements

Functional requirements describe **what the system must do**.

### FR1 — Delivery Request Management

The system shall allow authorized hospital staff to create a delivery request specifying the destination, medicine type, quantity, priority, and recipient.

**Acceptance criterion:** 100% of valid requests are recorded with a unique tracking ID.

### FR2 — Autonomous Navigation

The drone shall calculate and follow a flight route using positioning data, mapped obstacles, weather information, and approved flight corridors.

**Acceptance criterion:** In the defined route-test suite, the drone completes each route without unauthorized entry into restricted airspace.

### FR3 — Secure Medicine Storage

The drone shall lock its payload compartment during flight and restrict access to authorized personnel.

**Acceptance criterion:** All unauthorized access attempts in the defined security test suite are denied.

### FR4 — Real-Time Tracking

The system shall display the drone's location, flight status, estimated arrival time, and delivery status to authorized users.

**Acceptance criterion:** Position updates are displayed at least once every 5 seconds while connectivity is available.

### FR5 — Delivery Confirmation

The system shall verify receipt using an authorized recipient's authentication, a secure access code, or another approved method.

**Acceptance criterion:** Every completed delivery generates a timestamped receipt and recipient-verification record.

### FR6 — Emergency Handling

The system shall detect critical battery levels, navigation failures, and communication loss, then execute a predefined safe response.

**Acceptance criterion:** Every scenario in the approved emergency test suite triggers its specified safe-state procedure.

## 3. Non-Functional Requirements Using FURPS+

Non-functional requirements describe **how well the system must operate**.

### F — Functionality

Although functionality is commonly used to describe system capabilities, these targets add measurable completeness and access-control expectations.

- The system shall support at least 50 registered hospital delivery locations.
- It shall maintain an auditable record of 100% of medicine dispatches and deliveries.
- It shall reject delivery requests from unauthenticated users.
- It shall verify that the selected payload matches the authorized delivery request.

### U — Usability

- A trained staff member shall create a delivery request in no more than 2 minutes in at least 90% of usability tests.
- New staff shall complete a standard delivery request after no more than 30 minutes of training.
- The dashboard shall display active, delayed, completed, and failed deliveries using clearly distinguishable status labels.
- Critical alerts shall identify the problem and the required action.

### R — Reliability

- The system shall achieve at least 99% successful delivery completion across a defined set of eligible missions.
- The system shall automatically detect critical battery, navigation, and communication faults.
- It shall preserve delivery records during a temporary network outage and synchronize them after reconnection.
- It shall maintain the specified storage temperature range throughout every mission involving temperature-sensitive medicines.

### P — Performance

- The system shall process a valid delivery request within 3 seconds under normal operating load.
- The drone shall support a minimum payload of 2 kg, subject to engineering validation.
- The drone shall complete a 5 km one-way delivery within 15 minutes under defined test conditions.
- The tracking dashboard shall refresh location data every 5 seconds or less when the connection is available.

### S — Supportability

- The system shall record diagnostic events with timestamps and error codes.
- Authorized technicians shall be able to retrieve diagnostic logs within 5 minutes.
- Software updates shall be digitally signed and verified before installation.
- The system shall support remote software updates without deleting existing delivery records.

### + — Additional Constraints

**Safety**
- The drone shall enter a defined safe state when a critical fault is detected.
- Emergency procedures shall account for loss of communication, low battery, navigation faults, and unsafe landing conditions.

**Security**
- Data in transit shall use approved encryption.
- Administrative access shall require multi-factor authentication.
- Payload access and delivery records shall be auditable.

**Hardware and medicine integrity**
- The payload compartment shall maintain the medicine's specified temperature range for the duration of the mission.
- The drone shall not be dispatched if the payload, battery, or environmental conditions violate approved operating limits.

**Interfaces**
- The system shall exchange delivery status with the hospital's authorized information system through a documented API.
- Interface failures shall be logged and surfaced to authorized operators.

**Regulatory**
- All flights shall comply with applicable Ghana Civil Aviation Authority requirements and any required operational approvals.
- Medicine handling and transport shall comply with applicable healthcare and pharmaceutical requirements.

## 4. Summary Table

| Category | Example measurable requirement |
|---|---|
| Functionality | Every delivery has a unique tracking ID. |
| Usability | Create a delivery request within 2 minutes in at least 90% of tests. |
| Reliability | At least 99% successful completion of eligible missions. |
| Performance | Process a valid request within 3 seconds. |
| Supportability | Retrieve diagnostic logs within 5 minutes. |
| Safety (+) | Correctly respond to every scenario in the approved emergency test suite. |
| Security (+) | Deny all unauthorized access attempts in the defined test suite. |
| Regulatory (+) | Every operational flight complies with applicable aviation requirements. |

## 5. Making Requirements Measurable

Vague requirement:

> The drone should be fast.

Measurable alternative:

> The drone shall complete a 5 km one-way delivery within 15 minutes under specified wind, payload, and battery conditions in at least 95% of acceptance tests.

Vague requirement:

> The drone should be reliable.

Measurable alternative:

> The system shall achieve at least 99% successful delivery completion across the agreed population of eligible missions, measured over a defined test period and under specified operating conditions.

A complete requirement should define:
1. **The required behavior or quality**
2. **A measurable threshold**
3. **The conditions under which it is measured**
4. **The test or evidence used to verify it**

## 6. Conclusion

The FURPS+ model helps the project team distinguish between what the autonomous hospital drug delivery drone must do and the quality, safety, and regulatory constraints under which it must operate.

For a medical delivery system, flight safety, medicine integrity, secure custody, and regulatory compliance are critical constraints. They should not be traded away simply to improve speed or reduce cost.

## 7. Suggested Acceptance-Test Checklist

- [ ] Valid delivery requests receive unique tracking IDs.
- [ ] Unauthorized users cannot create delivery requests or open the payload compartment.
- [ ] Test routes avoid restricted airspace.
- [ ] Tracking updates meet the specified refresh interval when connectivity is available.
- [ ] Every completed delivery has a timestamped confirmation.
- [ ] All defined emergency scenarios trigger the correct safe response.
- [ ] Temperature-sensitive payloads remain within their specified temperature range.
- [ ] Diagnostic logs can be retrieved within the specified time.
- [ ] Software updates are verified before installation.
- [ ] Regulatory and operational approvals are confirmed before real-world flights.
