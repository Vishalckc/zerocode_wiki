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
`"steps":[{
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

  

      "assertions": {
        "status": 200

      }
    }]`

after replacing RANDOM.NUMBER placeholders,we get the following request:
`request:
{
  "headers" : {
    "Content-Type" : "application/json;charset=UTF-8"
  },
  "body" : {
    "orders" : [ {
      "orderId" : "6432473468588586502",
      "amount" : 5,
      "productName" : "product1"
    }, {
      "orderId" : "6249704932535842532",
      "amount" : 10,
      "productName" : "product2"
    } ]
  }
} `

every instance of RANDOM.NUMBER is unique


Using `${RANDOM.NUMBER.FIXED}`
===
sample step:
` {
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
              "orderId": "${RANDOM.NUMBER.FIXED}",
              "amount": 5,
              "productName": "product1"
            },
            {
              "orderId": "${RANDOM.NUMBER.FIXED}",
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
    },`

after `RANDOM.NUMBER.FIXED` placeholder are replaced we get the following request:

`request:
{
  "headers" : {
    "Content-Type" : "application/json;charset=UTF-8"
  },
  "body" : {
    "orders" : [ {
      "orderId" : "6598115625161692428",
      "amount" : 5,
      "productName" : "product1"
    }, {
      "orderId" : "6598115625161692428",
      "amount" : 10,
      "productName" : "product2"
    } ]
  }
} 
`


`RANDOM.NUMBER.FIXED` placeholders get the same random number value within the step






Using `${RANDOM.NUMBER:10}`
===
we can limit random numbers' length. In this case random numbers length(digit count) would be 10. 

Conclusion
===
Prodive the link to a "Hello World" test scenario which an end user can see-in-action ie a working code
