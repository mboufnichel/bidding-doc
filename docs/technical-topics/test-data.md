# Best Practices for Test Data in Unit and Integration Tests

## 1. Use Test Fixtures for Consistency
- Create reusable test data objects or builders for consistent setups.
- Example in Kotlin:
  ```kotlin
  object UserTestFixture {
      fun createValidUser(): User {
          return User(name = "Alice", email = "alice@xyz.com", isActive = true)
      }
  }

## 2. Ensure Idempotency
- Test data should not depend on the execution order of tests to avoid side effects from previous tests.
- Each test should be independent, meaning it can run in any order and still produce consistent results.
- Use **unique identifiers** (e.g., UUIDs) for test data to prevent conflicts between tests.

### Best Practices:
- **Avoid shared state** between tests.
- Use **UUIDs** or random values for IDs to ensure uniqueness:
  ```kotlin
  val userId = UUID.randomUUID().toString()
  val user = User(id = userId, name = "Alice", email = "alice@xyz.com")

## 3. Minimize Test Data Scope
- Provide **only the necessary data** for each test to ensure clarity and reduce complexity.
- Avoid loading unnecessary data or objects that aren't relevant to the specific test being executed.
- Keeping the test data minimal helps improve the speed and maintainability of tests.
