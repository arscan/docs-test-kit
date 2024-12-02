# ONC Certification (g)(10) Test Kit Developer's Guide

<!--
This is a comment intended for authors of this document to help guide useful content.
It may be deleted.

Test Kits should provide documentation on the process by which they are updated over time.
This template provides a a starting point for creating such documentation.  It is only
a suggestion; anything may be put in here.

This document should be committed with the Test Kit repository.
--->

Last updated: v0.0.0

## Introduction

This Developer Guide provides procedures and guidelines for maintaining and
updating the ONC Certification (g)(10) Test Kit.  The guide serves as the
primary reference for all development activities, including updates to
standards, bug fixes, and platform integration maintenance.

This document serves multiple purposes:
* To guide individuals who are interested in contributing to this project.
* To assist in the onboarding of new development team members.
* To support the long-term continuity of this project by enabling an
  effective transfer of this software to new stewards.

This document does not provide detailed instructions on how to use
an Inferno Test Kit, the contents of the (g)(10) Certification Criteria,
basics of the Inferno Framework, or details on how to use Ruby, Docker,
or other tools.  Developers are expected to have at least a basic understanding
of all these topics.  Please refer to the References section of this document
for links to more information about these topics.

Please note that the focus of this document are on features that are specific to
this Test Kit and does not provide a detailed explanation of common Inferno
Framework functionality.

## Test Kit Overview

The ONC Certification (g)(10) Standardized API Test Kit is a testing tool for
Health IT systems seeking to meet the requirements of the ONC Standardized API
for Patient and Population Services criterion § 170.315(g)(10) in the ONC
Certification Program.

Tests within the (g)(10) Standardized API Test Kit behave like an automated API
consumer, making a series of HTTP requests that mimic a real world client to
ensure that the API supports an approved version of each of the required
standards:

•	Health Level 7 (HL7®) Fast Healthcare Interoperability Resources (FHIR®) (v4.0.1)
•	US Core Implementation Guide (v3.1.1, v4.0.0, or v6.1.0)
•	SMART Application Launch Framework Implementation Guide Release (v1.0.0, or v2.0.0)
•	HL7 FHIR Bulk Data Access (Flat FHIR) (v1.0.1, or v2.0.0)


## Relationship with Other Test Kits

The ONC (g)(10) Certification Criterion requires the implementation of several
FHIR Implementation Guides, while providing guidance on how to support these
test kits to accomplish the specific requirements of the certification
criterion.  In order to facilitate testing systems independently of the (g)(10)
Certification requirements, each of these Implementation Guides also has a
stand-alone Test Kit.  The (g)(10) Test Kit then imports tests defined in these
Test Kits and integrates them into a single cohesive test procedure, while also
further constraining their implementation to meet any (g)(10)-specific
requirements.

This level of indirection facilitates use of these component test kit,
however, it does add some complexity to the maintenance of the (g)(10) Test Kit.
The specific Test Kits that are imported into this Test Kit include:

### US Core Test Kit

The purpose of the Inferno US Core Test Kit is to verify server’s conformance to
the US Core Implementation Guide (v3.1.1, v4.0.0, v5.0.1, v6.1.0, and future
release). This test kit is located on GitHub at
https://github.com/inferno-framework/us-core-test-kit.


### SMART App Launch Test Kit

The purpose of the Inferno SMART App Launch Test Kit is to confirm a server's
ability to provide authorization and/or authentication services to client
applications that access HL7® FHIR® APIs. This test kit is located on GitHub at
https://github.com/inferno-framework/smart-app-launch-test-kit.
 


<!-- 
Test Kits may be dependent on other Test Kits.  This section should describe
the relationship between this Test Kit and other Test Kits.

For example, a common situation is for a Test Kit to 

-->

## Test Kit Components

* One test suite
* One reference server
* Data for reference server
* Specialized Terminology checking and terminology preparation
* Documentation

## Test Kit Code Organization

The (g)(10) Test Kit follows general Ruby conventions for applications and
libraries.  It is organized into several main directories:

- `.github`: Contains workflows for integrating with GitHub's automated tools
- `bin`: Contains scripts for generating local terminologies.
- `config`: Contains configuration files for the test kit.
- `data`: Contains runtime data for the test kit, such as local database files
- `docs`: Contains documentation for this test kit.
- `lib`: Contains the main logic for the test kit, including the test cases and helper functions.
- `lib/inferno`: Contains patches to the Inferno Framework to accommodate special cases.
- `lib/onc_certification_g10_test_kit`: Contains the main tests for the test kit
- `resources`: Contains static resources such as FHIR profiles and test data.
- `spec`: Contains the RSpec test cases for the test kit.
- `tmp`: Temporary files used by the test kit at runtime.

The (g)(10) Test Kit contains a single suite of tests, which is capable of testing
any valid combination of approved standards for certification.  This suite
is defined in `lib/onc_certification_g10_test_kit.rb` and imports all necessary
tests from both external Test Kits and from within the (g)(10) Test Kit itself.


## Testing Approach

* users are required to pass all tests to demonstrate
conformance to the g10 certification criteria



## FHIR and Terminology Validation



## Unit Tests


## 


## Standards Version Update Process






## Updating to new versions of Ruby


## Updating Dependencies


Updating to new versions of Ruby
Updating versions of 


## What to do when profiles are incorrect




