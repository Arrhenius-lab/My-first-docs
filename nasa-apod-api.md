# NASA APOD API — Reference Documentation
GET /planetary/apod

## Overview
This endpoint returns a specific picture for a given date. A valid API key is required to access it, but it doesn't affect which picture is returned.

## Authentication
This endpoint requires an API key. You can either sign up on NASA's portal, or use DEMO_KEY for quick testing.

## Request Details
| Name | Type | Required? | Description | Example |  
|------|------|-----------|-------------|---------|  
| api_key| string | yes | Your NASA API key, used to authenticate the request | DEMO_KEY |  
| Date | string | no | The date of the APOD to retrieve, in YYYY-MM-DD format. Defaults to today's date if omitted | 2024-01-01 |

## Example Request
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=2024-01-01

## Example Response
{
  "date": "2024-01-01",
  "title": "NGC 1232: A Grand Design Spiral Galaxy",
  "explanation": "A description of the featured image or video.",
  "url": "https://apod.nasa.gov/apod/image/2401/ngc1232b_vlt_960.jpg",
  "hdurl": "https://apod.nasa.gov/apod/image/2401/ngc1232b_vlt_3969.jpg",
  "media_type": "image",
  "service_version": "v1"
}

- date: the date of the featured picture
- title: the title of the image or video
- explanation: a written description of what's shown
- url: link to the standard-resolution image
- hdurl: link to the high-definition version of the same image
- media_type: whether the content is an "image" or a "video" — check this before assuming it's a picture
- service_version: internal NASA API version number (not needed by most users)

## Error Handling
- A request with no date (or today's date) sometimes returns a 500 Internal Service Error — a known bug in NASA's APOD API. Workaround: always specify a past date explicitly.
- Missing or invalid api_key returns a 403 Forbidden error, since authentication failed.

## Try It
If you get a 500 error, try specifying an explicit past date rather than leaving the date parameter out.
