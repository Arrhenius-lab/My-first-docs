# Agify API — Reference Documentation

`GET /?name={name}`

## Overview

This endpoint guesses a person's age based on the person's name.

## Authentication

This endpoint does not require an API key. Anyone can use it freely.

## Request Details

| Name | Type | Required? | Description | Example |
|------|------|-----------|--------------|---------|
| name | string | Yes | The name to predict an age for | Ibrahim |

## Example Request

https://api.agify.io?name=Ibrahim

## Example Response

```json```
{"count":96227,"name":"Ibrahim","age":41}

- name: the person's age is guessed based on the person's name

- age: the person's age is guessed based on the person's name

- count: number of individuals bearing the name (used as evidence for the guess)

## Error Handling
- Error: "Missing 'name' parameter" — returned when the name parameter is left out of the request entirely.

- If the server is temporarily unavailable or overloaded, the API may return a 503 or similar error. Retry the request after a few seconds.

## Try It

If you don't receive a response, double check that the name parameter is spelled correctly and the request is a valid GET request.
Code

**Key lesson to remember going forward:** every single time you open a code block with ` ``` `, your eyes should immediately go hunting for its matching closing ` ``` ` before you move on — an unclosed code block breaks everything typed after it, exactly like what just happened here.

Replace that whole section, tap "Preview" to double check BEFORE committing, and tell me what you see.
