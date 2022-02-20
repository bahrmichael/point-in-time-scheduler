# Authorization

Document state: DRAFT

All APIs are secured with API keys. For the scheduler there are two types of API keys: Data keys and control keys.

---

**Warning**: API keys take about 60 seconds to fully initialize. If you get a `403` error, please wait for 30 seconds and then try again.

---

Data keys are required for all message related operations, such as `Schedule Message`, `List Messages`, and `Redrive Message`.

Control keys are required for all other operations, such as `Create Application`, `List Application`, and `Deactivate Data Key`.

## Data Key

You can generate a data key by going to an application, click on "API Keys" and then "Generate new API key".

Use the application ID and the API key for Basic authentication.

### Basic Authentication

To build the `Authorization` header, we need three steps. First, take the app ID and the api key, and concatenate them with a colon `:`. For example `123` and `S3crEt!` become `123:S3crEt!`. Then base64 encode the concatenated string. For example `123:S3crEt!` becomes `MTIzOlMzY3JFdCE=`. Finally, set the encoded value as the `Authorization` header. In our example this would look like the following:

```js
headers: {
  Authorization: "Basic MTIzOlMzY3JFdCE="
}
```

## Control Key

You can generate a control key by going the [https://app.point-in-time-scheduler.com/control-keys](https://app.point-in-time-scheduler.com/control-keys), and click on "Generate new Access Token".

To use the control key in operations, pass it as the `Authorization` header with a `Token` prefix. For example if your control key is `12345`, then pass it the following way:

```js
headers: {
  Authorization: "Token 12345"
}
```
