# Library App

## Description

The **Library App** is a console-based application designed to manage library operations such as patron management, book loans, and membership renewals. It uses JSON-based data storage and provides various services to handle library functionalities. The application is built with a modular architecture, leveraging dependency injection and repository patterns for scalability and maintainability.

## Project Structure

The project is organized into the following directories:

- **src**: Contains the source code for the application.
  - **Library.ApplicationCore**: Core application logic and domain entities.
    - `Entities/`
      - `Author.cs`
      - `Book.cs`
      - `BookItem.cs`
      - `Loan.cs`
      - `Patron.cs`
    - `Enums/`
      - `LoanExtensionStatus.cs`
      - `LoanReturnStatus.cs`
      - `MembershipRenewalStatus.cs`
    - `Interfaces/`
      - `IPatronRepository.cs`
      - `IPatronService.cs`
      - `ILoanRepository.cs`
      - `ILoanService.cs`
    - `Services/`
      - `PatronService.cs`
      - `LoanService.cs`
    - `Library.ApplicationCore.csproj`
  - **Library.Console**: Console application entry point and user interface logic.
    - `appSettings.json`
    - `CommonActions.cs`
    - `ConsoleApp.cs`
    - `ConsoleState.cs`
    - `Program.cs`
    - `Library.Console.csproj`
  - **Library.Infrastructure**: Handles data access and storage.
    - `Data/`
      - `JsonData.cs`
      - `JsonLoanRepository.cs`
      - `JsonPatronRepository.cs`
    - `Library.Infrastructure.csproj`
- **tests**: Contains unit tests for the application.
  - **UnitTests/**
    - `ApplicationCore/`
      - `LoanService/`
        - `ReturnLoan.cs`
        - `ExtendLoan.cs`
      - `PatronService/`
        - `RenewMembership.cs`
    - `UnitTests.csproj`

## Key Classes and Interfaces

- **Entities**

  - **Author**: Represents an author with properties like `Id` and `Name`.
  - **Book**: Represents a book with properties like `Id`, `Title`, `AuthorId`, `Genre`, `ImageName`, and `ISBN`.
  - **BookItem**: Represents a specific copy of a book with properties like `Id`, `BookId`, `AcquisitionDate`, and `Condition`.
  - **Loan**: Represents a loan with properties like `Id`, `BookItemId`, `PatronId`, `LoanDate`, `DueDate`, and `ReturnDate`.
  - **Patron**: Represents a library patron with properties like `Id`, `Name`, `MembershipStart`, `MembershipEnd`, and `Loans`.

- **Enums**

  - **LoanExtensionStatus**: Enum for loan extension statuses.
  - **LoanReturnStatus**: Enum for loan return statuses.
  - **MembershipRenewalStatus**: Enum for membership renewal statuses.

- **Interfaces**

  - **IPatronRepository**: Interface for patron repository with methods like `GetPatron`, `SearchPatrons`, and `UpdatePatron`.
  - **IPatronService**: Interface for patron service with method `RenewMembership`.
  - **ILoanRepository**: Interface for loan repository with methods like `GetLoan` and `UpdateLoan`.
  - **ILoanService**: Interface for loan service with methods like `ReturnLoan` and `ExtendLoan`.

- **Services**

  - **PatronService**: Implements `IPatronService` to handle patron-related operations.
  - **LoanService**: Implements `ILoanService` to handle loan-related operations.

- **Console**

  - **ConsoleApp**: Main console application class that handles user interactions and application flow.
  - **ConsoleState**: Enum for different states of the console application.
  - **CommonActions**: Enum for common actions in the console application.

- **Infrastructure**
  - **JsonData**: Handles loading and saving data to JSON files.
  - **JsonLoanRepository**: Implements `ILoanRepository` to manage loan data.
  - **JsonPatronRepository**: Implements `IPatronRepository` to manage patron data.

## Usage

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd LibraryApp
   ```
2. Open the solution file `AccelerateDevGitHubCopilot.sln` in Visual Studio.
3. Build the solution to restore dependencies:
   ```bash
   dotnet build
   ```
4. Run the `Library.Console` project to start the console application:
   ```bash
   dotnet run --project src/Library.Console
   ```
5. Follow the on-screen instructions to search for patrons, view patron details, extend loans, return books, and renew memberships.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
