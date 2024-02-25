# TikTok-Research-API
<a target="_blank" href="https://colab.research.google.com/github/HenryBlackie/TikTok-Research-API/blob/main/TikTok_Research_API.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

## What?
This is a simple toolkit for exporting data via the TikTok Research API. It follows all rules and restrictions outlined by the [TikTok Research API Terms of Service](https://www.tiktok.com/legal/page/global/terms-of-service-research-api/en).

This project is still in the early stages of development. The provided code should work in most situations but it has only been lightly tested and does not currently handle errors gracefully, so I would highly recommend verifying any outputs.

### Capabilities
- Export comments from a single video
- Export a list of uploaded videos by a single user between two dates
- Export comments from uploaded videos by a single user between two dates
- Save exported data to Google Drive

### Future Improvements
- [ ] Add proper error handling
- [ ] Add code to detect and report expired/invalid client keys, secrets, and tokens
- [ ] Add code to report exceeded quota limits

## Why?
When I first started working on this notebook there was very little documentation available related to the research API and the few code examples I could find did not suit my needs.

## How?
> [!IMPORTANT]
> Before you can use this notebook you must get approval from TikTok to access to their Research API. More information can be found here: https://developers.tiktok.com/products/research-api/

### Initial Setup
#### TikTok Client Setup
You must provide a client_key and client_secret before running any of the other cells, without this the notebook will not be able to generate a valid access token.
#### Setup Google Drive
This cell will run through the Google Drive authentication process, you can change the output root directory if desired.

### Extraction
#### Get Video Comments
Will attempt to scrape comments from the specified video and export them to an Excel spreadsheet.
#### Get User Data
This will identify all user uploaded videos between the provided dates and then will attempt to scrape the comments from each video. The video details will be exported to a single Excel file and the comments will be exported to separate Excel files. If no dates are provided then the search will be between `2016-09-20` and `current_date`, which should cover everything since the initial release of TikTok.
Due to API limitations, this function will send a lot of queries. If the target account uploads frequently or their posts get a lot of engagement, you may be unable to get all of their data before reaching the API daily quota.
### Debugging
The cells in this section will not export any data, they are just intended for debugging when other functions are not working as expected.

## Useful References
[TikTok Research API - Frequently Asked Questions](https://developers.tiktok.com/doc/research-api-faq)
