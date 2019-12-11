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
    {"LifeCycleStatusName": "Rejected: ${reasonForRejection}", "LifeCycleStatus": "R"}
    ```
- Action Parameter
    ```
    reasonForRejection
    ```

# LCS Helper

- HTML Text
    
    ```
    {{lcsHelper dataSets.[0].data.d.LifeCycleStatusName}}
    ```

- Function Handler
    
    ```
    Handlebars.registerHelper("lcsHelper", function (passedString) {
    if (passedString.includes("A")) {
    return new Handlebars.SafeString( "<img src='green.png' style=' width: 24px; height: 24px;'>");
    }
    if (passedString.includes("R")) {
    return new Handlebars.SafeString("<img src='yellow.png' style=' width: 24px; height: 24px;'>");
    }
    return new Handlebars.SafeString( "<img src='red.png' style=' width: 24px; height: 24px;'>");
    });
    ```
