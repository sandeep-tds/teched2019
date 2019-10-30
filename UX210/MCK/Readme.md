# MCK Demo

This file will have all the material needed to build a demo app.

# Project Name

```
teched.mck
```

# Action - 1 Accept

- URL
    ```
    /SalesOrderHeaders('${SalesOrderId}')
    ```
- Body
    ```
    {"LifeCycleStatusName": "Accepted", "LifeCycleStatus": "A"}
    ```

# Action - 2 Reject

- URL
    ```
    /SalesOrderHeaders('${SalesOrderId}')
    ```
- Body
    ```
    {"LifeCycleStatusName": "Rejected: ${reasonForRejection}", "LifeCycleStatus": "A"}
    ```
- Action Parameter
    ```
    reasonForRejection
    ```