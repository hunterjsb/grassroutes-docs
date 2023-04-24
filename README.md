# `/preload` Endpoint

## Description
This endpoint preloads data for the application based on the given optional parameters.

## Request
- Method: GET
- URL: `/preload`
- Example: GET `/preload?pos=false`

## Parameters
- `invoices` (bool, optional): If `true`, preload invoice data. Default value is `true`.
- `pos` (bool, optional): If `true`, preload purchase orders data. Default value is `true`.

## Headers
- `Authorization` (string): The authorization token for accessing the endpoint.

`Authorization: Bearer YOUR-API-KEY`

## Response
- `200 OK`: The data has been preloaded successfully.
    - Content-Type: `application/json`
    - Body:
        ```
        {
            "status": "success",
            "message": "Data preloaded successfully."
        }
        ```
- `401 Unauthorized`: The provided authorization token is invalid.
    - Content-Type: `application/json`
    - Body:
        ```
        {
            "status": "error",
            "message": "Invalid authorization token."
        }
        ```
- `400 Bad Request`: The provided parameters are invalid.
    - Content-Type: `application/json`
    - Body:
        ```
        {
            "status": "error",
            "message": "Invalid parameters."
        }
        ```
