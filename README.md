# Lokalise Fastlane Actions

Collection of actions for integrating Lokalise into your iOS project using Fastlane. Learn more in our [blog post.](https://blog.lokalise.com/automating-itunes-connect-deployment-with-fastlane-and-lokalise/)

For Android actions please check [here](https://github.com/lokalise/lokalise-fastlane-actions/tree/master/android)

## Note

These are Fastlane actions, not plugins. Add them to `fastlane/actions` folder in the root of your project.

## lokalise

This action downloads .strings and .stringsdict files to destination folder.

Parameters:

- `api_token`. Your API token. Can be set up using enviromental parameter `LOKALISE_API_TOKEN`
- `project_identifier`. Your Project ID. Can be set up using enviromental parameter `LOKALISE_PROJECT_ID`
- `destination`. Localization files destination.
- `clean_destination`. Cleans destination folder if set to `true` *(`false` by default)*.
- `languages`. Languages to download *(must be passed as array of strings, leave empty to download all)*.
- `include_comments`. Include comments in exported files.
- `use_original`. Use original filenames/formats.

## lokalise_metadata

This action imports metadata from files generated by Deliver action and uploads iTunes Connect metadata using information from Lokalise.

- `api_token`. Your API token. Can be set up using enviromental parameter `LOKALISE_API_TOKEN`
- `project_identifier`. Your Project ID. Can be set up using enviromental parameter `LOKALISE_PROJECT_ID`
- `action`. Action to perform *(can be `update_lokalise_itunes`, `update_itunes`, `update_lokalise_googleplay` or `update_googleplay`)*. 
- `add_languages`. Add missing languages to lokalise *(`false` by default)*.
- `override_translation`. Override translations in lokalise.
- `release_number`. Application release number. Required with `update_googleplay` action.
- `validate_only`. Only validate the metadata. Used with `update_googleplay` action *(`false` by default)*.

## add_keys_to_lokalise

This actions allow you upload keys to Lokalise.

Parameters:

- `api_token`. Your API token. Can be set up using enviromental parameter `LOKALISE_API_TOKEN`
- `project_identifier`. Your Project ID. Can be set up using enviromental parameter `LOKALISE_PROJECT_ID`
- `platform_mask`. Platform mask to asign to keys *(1 is iOS, 2 is Android, 4 is Web and 16 is Other)*.
- `keys`. Keys to add *(must be passed as array of strings)*.

