swagger: "2.0"
x-collection-name: Allied Irish Bank
x-complete: 1
info:
  title: Allied Irish Bank
  description: this-is-an-openapi-definition-for-the-standard-set-of-open-banking-httpopenbankingapis-io-apis-covering-the-allied-irish-bank-apis-
  termsOfService: https://www.openbanking.org.uk/open-licence/
  contact:
    name: API Evangelist
    url: https://apievangelist.com
    email: info@apievangelist.com
  version: 1.0.0
basePath: open-banking/v2.1/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /payment-submissions:
    post:
      summary: Create a payment submission
      description: Submit a previously setup payment
      operationId: CreatePaymentSubmission
      x-api-path-slug: paymentsubmissions-post
      parameters:
      - in: header
        name: Authorization
        description: An Authorisation Token as per https://tools
      - in: body
        name: body
        description: Setup a single immediate payment
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: x-fapi-customer-ip-address
        description: The PSUs IP address if the PSU is currently logged in with the
          TPP
      - in: header
        name: x-fapi-customer-last-logged-time
        description: The time when the PSU last logged in with the TPP
      - in: header
        name: x-fapi-financial-id
        description: The unique id of the ASPSP to which the request is issued
      - in: header
        name: x-fapi-interaction-id
        description: An RFC4122 UID used as a correlation id
      - in: header
        name: x-idempotency-key
        description: Every request will be processed only once per x-idempotency-key
      - in: header
        name: x-jws-signature
        description: DO NOT USE
      responses:
        200:
          description: OK
      tags:
      - Banking
      - Payments
      - Submissions
  /payment-submissions/{PaymentSubmissionId}:
    get:
      summary: Get a payment submission
      description: Get payment submission
      operationId: GetPaymentSubmission
      x-api-path-slug: paymentsubmissionspaymentsubmissionid-get
      parameters:
      - in: header
        name: Authorization
        description: An Authorisation Token as per https://tools
      - in: path
        name: PaymentSubmissionId
        description: Unique identification as assigned by the ASPSP to uniquely identify
          the payment submission resource
      - in: header
        name: x-fapi-customer-ip-address
        description: The PSUs IP address if the PSU is currently logged in with the
          TPP
      - in: header
        name: x-fapi-customer-last-logged-time
        description: The time when the PSU last logged in with the TPP
      - in: header
        name: x-fapi-financial-id
        description: The unique id of the ASPSP to which the request is issued
      - in: header
        name: x-fapi-interaction-id
        description: An RFC4122 UID used as a correlation id
      responses:
        200:
          description: OK
      tags:
      - Banking
      - Payments
      - Submissions
host: openapi.aibgb.co.uk