# Airport SDK

## Overview

The Airport Info API is a powerful tool for obtaining detailed information about airports worldwide. This API provides data such as IATA code, ICAO code, airport name, city name, country code, geographical coordinates, and time zone.

### Available Operations

* [airportInfo](#airportinfo) - Get airport information

## airportInfo

Get airport information

### Example Usage

```typescript
import { Airport } from "Airport";
import { AirportInfoResponse } from "Airport/dist/sdk/models/operations";

const sdk = new Airport();

sdk.airport.airportInfo({
  query: "query Query($request: AirportRequest) { AirportInfo(request: $request) { result { city { iata_country_code iata_code id name } city_name iata_code iata_country_code icao_code id latitude longitude name time_zone } error { description } } }",
  variables: {
    request: {
      iata: "LHR",
    },
  },
}, {
  bearerAuth: "Bearer YOUR_BEARER_TOKEN_HERE",
}).then((res: AirportInfoResponse) => {
  if (res.statusCode == 200) {
    // handle response
  }
});
```
