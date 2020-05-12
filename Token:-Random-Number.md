## Contents
   * [Flavors of Random Number](#flavors-of-random-number)
   * [Usecases of Random Numbers](#usecases-of-random-number)
   * [Using ${RANDOM.NUMBER}](#using-randomnumber)
   * [Using ${RANDOM.NUMBER.FIXED}](#using-randomnumberfixed)
   * [Using ${RANDOM.NUMBER:10}](#using-randomnumber10)
   * [Conclusion](#conclusion)

Flavors of Random Number
===
to do

Usecases of Random Number
===
to do


Using `${RANDOM.NUMBER}`
===
todo


Using `${RANDOM.NUMBER.FIXED}`
===
sample step:

`{
      "name": "mytest",
      "url": "/orders",
      "operation": "POST",
      "request": {
        "headers": {
          "Content-Type": "application/json;charset=UTF-8"
        },
        "body": {
          "orders": [
            {
              "orderId": "${RANDOM.NUMBER}",
              "amount": 5,
              "productName": "product1"
            },
            {
              "orderId": "${RANDOM.NUMBER}",
              "amount": 10,
              "productName": "product2"
            }
          ]
        }
      },

      "retry":{
        "max": 2,
        "delay": 500
      },

      "assertions": {
        "status": 200

      }
    }`


Using `${RANDOM.NUMBER:10}`
===
todo : Explain the limit... 

Conclusion
===
Prodive the link to a "Hello World" test scenario which an end user can see-in-action ie a working code
