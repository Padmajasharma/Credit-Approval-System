# Credit Approval System Documentation

This project implements a **Credit Approval System** that evaluates loan eligibility using past loan data. It provides a set of APIs to manage customer information, assess loan eligibility, process loans, and retrieve loan-related details.

## Key Features

- **Add New Customers**: Insert customer information into the system.
- **Loan Eligibility Check**: Evaluate eligibility based on the customer's credit score.
- **Process New Loans**: Approve and manage loans for eligible customers.
- **Loan and Customer Details**: Retrieve information on specific loans and customers.
- **Customer-Wide Loan Summary**: View all active loans for a given customer.

## Technologies

- **Backend Framework**: Django  
- **Database**: PostgreSQL  
- **Containerization**: Docker, Docker Compose  

## API Endpoints

All API endpoints are available under the `/api/v1/` path. Ensure all endpoints include a trailing slash (`/`):

1. `/register/` - Register a new customer.
2. `/check-eligibility/` - Verify loan eligibility based on the credit score.
3. `/create-loan/` - Process and approve a loan for eligible customers.
4. `/view-loan/<loan_id>/` - Fetch details of a specific loan and its associated customer.
5. `/view-loans/<customer_id>/` - Retrieve all active loans for a specific customer.

## Pre-requisites

Ensure you have the following installed:

- **Python**  
- **Docker** and **Docker Desktop**  
- **Docker Compose**  

## Steps to Run the Application

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Padmajasharma/credit_approval_system.git
   ```
2. **Navigate to the project directory:**
   ```bash
   cd credit_approval_system
   ```
3. **Start Docker:**
   Start the Docker engine using Docker Desktop or through [system utilities](https://docs.docker.com/config/daemon/start/).

4. **Run the application with Docker Compose:**
   ```bash
   docker-compose up
   ```
5. **Access the API locally:**
   ```
   http://localhost:8000/api/v1/
   ```

## Testing the APIs

You can test the application using the provided Postman collection.  
[Postman Collection Link](https://www.postman.com/telecoms-geologist-66457404/workspace/open/collection/26309885-7d351ebb-b7c9-4ee6-8447-239e59c549bc)

### Steps for Postman Testing:
- **Change the agent**: If using Postman in a browser, switch to a [desktop agent](https://www.postman.com/downloads/postman-agent/). This option is located in the bottom-right corner of Postman.

## Configuring Production Secrets

To run the application securely, you need to set a production-grade secret key in an `.env` file:

1. **Generate a Django secret key:**
   ```python
   from django.core.management.utils import get_random_secret_key
   get_random_secret_key()
   ```
2. **Create an `.env` file** in the project's root directory and add the secret key:
   ```bash
   SECRET_KEY=your_secret_key_here
   ```
3. **Security Note**: Replace the default insecure key to protect against attacks.

