## Challenge: Serverless Weather Data Processor

### Overview
In this challenge, you will create a serverless application that fetches weather data from an external API, processes it, and stores it in a DynamoDB table. The application will also expose an endpoint through API Gateway that allows users to retrieve the processed data.

### Requirements

1. **Fetch Weather Data**: Create a Lambda function (`FetchWeatherData`) in Python that fetches weather data from an external API (such as OpenWeatherMap or Weatherstack). The function should be triggered by an API Gateway.

2. **Process and Store Weather Data**: After fetching the data, the `FetchWeatherData` function should process the data and store it in a DynamoDB table.

3. **Retrieve Weather Data**: The same API Gateway that triggers the `FetchWeatherData` function should also expose an endpoint to retrieve the stored weather data from the DynamoDB table. This endpoint should trigger the same Lambda function (`FetchWeatherData`) that fetches the data from the DynamoDB table and returns it.

### Evaluation Criteria

1. The application fetches, processes, and stores weather data correctly.
2. The API Gateway endpoint works as expected.

### Tips for Coding and Configuration

- **Lambda Functions**: When coding your Lambda functions in Python, make sure to handle any exceptions and include logging so you can troubleshoot any issues that arise. Use the `boto3` library to interact with AWS services such as DynamoDB.

- **API Gateway**: When configuring your API Gateway, create a new REST API and define resources and methods for your endpoints. Make sure to integrate your API methods with the correct Lambda functions.

- **DynamoDB Table**: When setting up your DynamoDB table, carefully consider your read and write capacity settings based on the expected traffic. Also, design your table structure and indexes based on the queries you'll be making.

- **Testing**: Test your application thoroughly. Use unit tests for your Lambda functions and use tools like Postman to test your API Gateway endpoints.

Good luck!