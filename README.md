Prerequisites
=============

* node latest version
* npm
* mongoDB

Installation
============

From the root folders of the project execute:

```bash
npm install 
```

Configuration
=============

Edit config.json to mtach your enviornment.

```bash
gulp nodemon
```

api details:
============

1) url: localhost:5001/bank/create-bank-account

params: 

{
	"account_number": 5566,
	"account_name": "Priya",
	"ifsc_code": "ICIC0000003",
	"password": "pass12",
	"currency": "INR",
	"balance": 5000
}

response:

{
  "success": true,
  "message": "account created successfully"
}

2) url: localhost:5001/bank/login

params: 

{
	"account_number": 5566,
	"password": "pass12"
}

response:

{
  "success": true,
  "message": "user login successfully",
  "data": {
    "account_number": 5566,
    "session_id": "9d513fa4-9a2d-480e-b921-e2d4745c55e3"
  }
}

3) url: localhost:5001/bank/balance-info

params:

{
	"account_num": 5566,
	"sid": "9d513fa4-9a2d-480e-b921-e2d4745c55e3"
}

response:

{
  "success": true,
  "data": {
    "account_number": 5566,
    "balance": 5000,
    "currency": "INR"
  }
}

4) url: localhost:5001/bank/add-beneficiary

params:

{
	"account_num": 5566,
    "sid": "9d513fa4-9a2d-480e-b921-e2d4745c55e3",
	"beneficiary": {
		"account_number": 67891,
		"account_name": "Lisa",
		"ifsc_code": "ICIC0000003"
	}
}

response:

{
  "success": true,
  "message": "beneficiary added successfully",
  "data": {
    "account_number": 67891,
    "beneficiaries": [
      {
        "account_number": 67891,
        "account_name": "Lisa"
      }
    ]
  }
}

5) url: localhost:5001/bank/transaction

params:

{
	"account_num": 5566,
    "sid": "9d513fa4-9a2d-480e-b921-e2d4745c55e3",
	"beneficiary": {
		"account_number": 67891,
		"account_name": "Lisa",
		"ifsc_code": "ICIC0000003",
		"date":"03-06-2017",
		"amount": 400
	}
}

response:

{
  "success": true,
  "message": "transaction successfull"
}

6) url: localhost:5001/bank/statement

params:

{
	"account_num": 5566,
    "sid": "9d513fa4-9a2d-480e-b921-e2d4745c55e3",
	"from":"01-06-2017",
	"to":"06-06-2017"
}

response:

{
    "success": true,
    "data": [
        {
            "tran_date": "2017-03-05T18:30:00.000Z",
            "particulars": "67891/Lisa",
            "debit": 400,
            "credit": null,
            "balance": 4600,
            "_id": "59379910e69f2c0e23a6ce9f"
        },
        {
            "tran_date": "2017-01-05T18:30:00.000Z",
            "particulars": "67891/Lisa",
            "debit": 400,
            "credit": null,
            "balance": 4200,
            "_id": "593799f6e69f2c0e23a6cea1"
        },
        {
            "tran_date": "2017-05-05T18:30:00.000Z",
            "particulars": "67891/Lisa",
            "debit": 400,
            "credit": null,
            "balance": 3800,
            "_id": "593799fde69f2c0e23a6cea3"
        },
        {
            "tran_date": "2017-06-05T18:30:00.000Z",
            "particulars": "67891/Lisa",
            "debit": 400,
            "credit": null,
            "balance": 3400,
            "_id": "59379b48e69f2c0e23a6cea5"
        }
    ]
api details:
============

1) url: localhost:5001/bank/create-bank-account

params: 

{
	"account_number":328416,
	"account_name": "Arisha Barron",
	"ifsc_code": "IOB0000001",
	"password": "admin12",
	"currency": "INR",
	"balance": 5000
}

response:

{
  "success": true,
  "message": "account created successfully"
}

2) url: localhost:5001/bank/login

params: 

{
	"account_number":328416,
	"password": "admin12"
}

response:
{
    "success": true,
    "message": "user login successfully",
    "data": {
        "account_number": 328416,
        "session_id": "32be3ac7-1d9c-4041-803f-d1e66b33e575"
    }
}

3) url: localhost:5001/bank/balance-info

params:
{
        "account_num":328416,
        "session_id": "f29a2fe5-1f65-498e-bf86-d5d943749d1f"
    }

response:

{
    "success": true,
    "data": {
        "account_number": 328416,
        "balance": 5000,
        "currency": "INR"
    }
}

4) url: localhost:5001/bank/add-beneficiary

params:
{
        "account_num":328416,
        "session_id": "f29a2fe5-1f65-498e-bf86-d5d943749d1f",
        "beneficiary": {
		"account_number":32156,
		"account_name": "Branden Gibson",
		"ifsc_code": "ICIC0000004"
	}
    }

response:
{
    "success": true,
    "message": "beneficiary added successfully",
    "data": {
        "account_number": 32156,
        "beneficiaries": [
            {
                "account_number": 32156,
                "account_name": "Branden Gibson"
            }
        ]
    }
}

5) url: localhost:5001/bank/transaction

params:
{
        "account_num":328416,
        "session_id": "f29a2fe5-1f65-498e-bf86-d5d943749d1f",
        "beneficiary": {
		"account_number":32156,
		"account_name": "Branden Gibson",
		"ifsc_code": "ICIC0000004",
        "date":"02-02-2021",
		"amount": 600
	}
    }

response:

{
  "success": true,
  "message": "transaction successfull"
}

6) url: localhost:5001/bank/statement

params:
{
        "account_num":328416,
        "session_id": "f29a2fe5-1f65-498e-bf86-d5d943749d1f",
        "from":"01-02-2021",
	"to":"02-02-2021"
        
    }

response:
{
    "success": true,
    "data": [
        {
            "_id": "601852e102440a2790d3e30a",
            "tran_date": "2021-02-01T18:30:00.000Z",
            "particulars": "32156/Branden Gibson",
            "debit": 600,
            "credit": null,
            "balance": 4400
        },
        {
            "_id": "601853d402440a2790d3e30d",
            "tran_date": "2021-02-01T18:30:00.000Z",
            "particulars": "32156/Branden Gibson",
            "debit": 600,
            "credit": null,
            "balance": 3800
        }
    ]
}
}


