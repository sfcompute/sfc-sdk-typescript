# MarketApiAllocationSchedule

## Example Usage

```typescript
import { MarketApiAllocationSchedule } from "@sfcompute/sdk/models";

let value: MarketApiAllocationSchedule = {
  total: [],
  byZone: {
    "key": [
      {
        effectiveAt: 1738972800,
        nodeAllocation: 299032,
      },
    ],
    "key1": [
      {
        effectiveAt: 1738972800,
        nodeAllocation: 299032,
      },
    ],
    "key2": [
      {
        effectiveAt: 1738972800,
        nodeAllocation: 299032,
      },
    ],
  },
};
```

## Fields

| Field                                                                                     | Type                                                                                      | Required                                                                                  | Description                                                                               |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `total`                                                                                   | [models.MarketApiScheduleEntry](../models/market-api-schedule-entry.md)[]                 | :heavy_check_mark:                                                                        | Capacity availability over time.                                                          |
| `byZone`                                                                                  | Record<string, [models.MarketApiScheduleEntry](../models/market-api-schedule-entry.md)[]> | :heavy_check_mark:                                                                        | Allocation schedule on a zone-by-zone basis. Only includes current and future schedule.   |