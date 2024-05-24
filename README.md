# Uplight-API-Functional-Testing
Quality Engineering: API Testing Project - Uplight

**Postman framework setup:**
Tinker around with the OpenVerse API: https://api.openverse.engineering/v1/ and
create a basic automation framework using Postman and Java script to test
the standard operations of the API and create test cases.

**Scenario 1: POST /v1/auth_tokens/register/** 
**Happy Path :**

Test the standard operations of the API and create test cases (Positive and Negative) for below endpoint
● POST /v1/auth_tokens/register/ (After this endpoint is hit, you must manually click a
link that is sent to you as an email before you can test the other endpoints.)
Automation part :
Request:
New random name and email will get generated every time when this end point will be called.
client_id and client_secret received in the response will be saved into collections variable

Response:
Assertions have been added to verify -
A) API response code - 201 created
B) API response schema
C) Response Data

**Negative tests:**

Negative test case 1 - Register application with same name :
Automation part :
Response:
Assertions have been added to verify -
A) API response code - 400
B) API responsedata error

Negative test case 2 - Register application with invalid email :
Automation part :
Response:
Assertions have been added to verify -
A) API response code - 400
B) API responsedata error

Negative test case 3 - Register application with missing name and email :
Automation part :
Response:
Assertions have been added to verify -
A) API response code - 400
B) API responsedata error

**Scenario 2  POST /v1/auth_tokens/token/**

**Happy Path:**
Get an access token using client credentials and create positive and negative tests for the end point
● POST /v1/auth_tokens/token/
Automation part :
Request:
client_id and client_secret received from the /auth_token/register will be passed into this end point.
access_token and token_type received in the response will be saved into the collections variable

Response:
Assertions have been added to verify -

A) API response code - 200 - access token generated successfully
B) API response schema - token_type should be 'bearer' for the new access token

**Negative test:**

Negative test case - Call auth_token end point with invalid / missing grant_type:
Automation part :
Response:
Assertions have been added to verify -
A) API response code - 400
B) API responsedata error

**Scenario 3 - GET /v1/audio/**
**Bonus test added**

Get a list of all audio files in the Openverse catalog and create positive and negative tests for the end point
● GET /v1/audio/
Automation part :
Response:
Assertions have been added to verify -

A) API response code - 200
B) API response schema


**Bonus Test has been coded to verify:**
Assert the first entry in results array has the field “id”
the value of "id" is a valid UUID v4

**Scenario 4 - GET /v1/audio/stats/**

Get a list of all content providers and their respective number of audio files in the Openverse catalog and create positive and negative tests for the end point
● GET /v1/audio/stats/
Automation part :
Response:
Assertions have been added to verify -

A) API response code - 200
B) API response data

**Bonus Test has been coded to**

Automate the email verification process

