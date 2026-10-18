# AWS Employee Purchase Approval Workflow

## Project Overview

This project demonstrates a serverless employee purchase approval workflow built using Amazon Web Services (AWS).

The workflow processes employee purchase requests, evaluates the purchase amount, and stores the processing result as a JSON object in Amazon S3.

This collaborative project was completed as part of our AWS training at Metropolia University of Applied Sciences.

## AWS Services Used

- **AWS Lambda:** Executes Python code to process employee purchase requests.
- **AWS Step Functions:** Orchestrates the purchase processing workflow.
- **Amazon S3:** Stores the processing results as JSON objects.

## Purchase Approval Rules

The workflow evaluates purchase requests according to the configured business rules:

| Purchase Amount | Status |
|---|---|
| €100 or less | `APPROVED` |
| Above €100 and up to €500 | `NEEDS_REVIEW` |
| Above €500 | `REJECTED` |

## Workflow

1. A purchase request is provided as input to the Step Functions workflow.
2. AWS Step Functions coordinates the processing.
3. The `ProcessPurchase` Lambda function evaluates the purchase amount.
4. The request is assigned a status according to the configured approval rules.
5. The processing result is stored as a JSON object in Amazon S3.

## Example Test Input

```json
{
  "RequestId": "test-002",
  "EmployeeId": "E1001",
  "PurchaseAmount": 250,
  "PurchaseItem": "Wireless mouse"
}
```

### Expected Result

For this test request, the expected status is `NEEDS_REVIEW` because the purchase amount is €250.

## Project Structure

The repository will include the project documentation and, once added, the Python source code and relevant screenshots.

```text
aws-employee-purchase-approval-workflow/
├── README.md
├── src/
└── screenshots/
```

## Key Learning Outcomes

- Understanding serverless architecture in AWS.
- Learning how AWS Step Functions orchestrates workflow execution.
- Working with Python-based AWS Lambda functions.
- Storing workflow results in Amazon S3.
- Testing and understanding a cloud-based business process.

## Team Project

This project was developed collaboratively with three fellow students during AWS training at Metropolia University of Applied Sciences.

## Future Improvements

- Add an API endpoint for submitting purchase requests.
- Introduce email notifications for purchase status updates.
- Improve error handling and monitoring.

## Author

Mehak Ali

## Technologies

AWS Lambda | AWS Step Functions | Amazon S3 | Python
