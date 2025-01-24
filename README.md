Currency Converter API
----------------------------------------
This is a Spring Boot application that integrates with a public API to provide real-time currency conversion functionality. It includes endpoints to fetch exchange rates and convert
currency amounts.
Technologies Used
● Java 21
● Spring Boot
● Maven
● External API: Exchange Rates API (or any other public API of your choice)
Features
1. GET /api/rates?base=USD: Fetch exchange rates for the specified base currency
(default is USD).
2. POST /api/convert: Convert an amount from one currency to another.
Installation
Prerequisites
Ensure you have the following installed:
● Java 21 or higher
● Maven
● Git (for cloning the repository)
Steps to Run the Application Locally
● Clone the repository:
git clone https://github.com/yourusername/currency-converter.git
● Navigate to the project directory:
cd currency-converter
1. Configure the API key:
○ Sign up for an API key from the external API provider (e.g., Exchange Rates
API).
○ Add your API key to the configuration.
● Run the application:
2. Access the application: The application should now be running locally at
http://localhost:8080.
API Endpoints
1. GET /api/rates
Fetch exchange rates for the specified base currency.
Query Parameters:
● base: (optional, default: "USD") Base currency.
Request Example:
http
CopyEdit
● GET /api/rates?base=USD
Response Example:
json
CopyEdit
{
"USD": 1.0,
"EUR": 0.9,
"JPY": 110.0
}
2. POST /api/convert
Convert an amount from one currency to another.
Request Body:
{
"from": "USD",
"to": "EUR",
"amount": 100
}
Response Example:
{
"from": "USD",
"to": "EUR",
"amount": 100,
"convertedAmount": 94.5
}
Error Handling
● 400 Bad Requests : Invalid or missing parameters.
● 404 Not Found: Currency code not recognized.
● 500 Internal Server Error: External API failure or unexpected error.
