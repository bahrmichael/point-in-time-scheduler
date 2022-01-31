# Authorization

Document state: DRAFT

All APIs are secured with API keys. For the scheduler there are two types of API keys: Data keys and control keys.

Data keys are required for all message related operations, such as `Schedule Message`, `List Messages`, and `Redrive Message`.

Control keys are required for all other operations, such as `Create Application`, `List Application`, and `Deactivate Data Key`.
