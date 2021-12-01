# RML-LDES-prototype

Prototype with BlueBike data to combine [RML](https://rml.io/spec) with [LDES](https://semiceu.github.io/LinkedDataEventStreams).

## Github Action configuration

This repository contains a Github Action setup to automatically generate 
LDES data using RML of the BlueBike API. 
This API is confidential and must be provided as a Github Repository Secret.

1. Go to *Settings* > *Secrets*
2. Create a new secret using the *New Repository Secret* button
3. Use `BLUEBIKE_API_URL` as name and the URL as value.
Note that the URL must be escaped for `sed`!

Example:

```
Name: BLUEBIKE_API_URL
Value: https:\/\/example.com\/api
```

## License

Released under the MIT license.
(c) Dylan Van Assche (2021)
IDLab - Ghent University - imec
