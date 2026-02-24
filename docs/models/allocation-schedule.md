# AllocationSchedule

## Example Usage

```typescript
import { AllocationSchedule } from "@sfcompute/sdk/models";

let value: AllocationSchedule = {
  total: [],
  byZone: {
    "key": [],
    "key1": [],
  },
};
```

## Fields

| Field                                                                                   | Type                                                                                    | Required                                                                                | Description                                                                             |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `total`                                                                                 | [models.ScheduleEntry](../models/schedule-entry.md)[]                                   | :heavy_check_mark:                                                                      | Capacity availability over time.                                                        |
| `byZone`                                                                                | Record<string, [models.ScheduleEntry](../models/schedule-entry.md)[]>                   | :heavy_check_mark:                                                                      | Allocation schedule on a zone-by-zone basis. Only includes current and future schedule. |