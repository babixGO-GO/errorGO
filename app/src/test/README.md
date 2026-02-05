# Android Unit Test Templates

This directory contains comprehensive unit test templates for Android development using JUnit and Mockito.

## Test Files

### 1. ExampleUnitTest.kt
Basic unit test template demonstrating:
- JUnit test structure (Given-When-Then pattern)
- Mockito mocking
- Basic assertions
- Null safety testing
- Collection operations testing
- Exception testing

### 2. ViewModelTestTemplate.kt
Template for testing Android ViewModels with:
- LiveData testing with InstantTaskExecutorRule
- Kotlin Coroutines testing
- Test dispatcher setup
- Async operation testing
- Error handling verification
- Loading state testing

### 3. RepositoryTestTemplate.kt
Template for testing Repository pattern with:
- API and Database mocking
- Data fetching and caching patterns
- Error handling
- CRUD operations testing

## Dependencies Required

Add these dependencies to your `app/build.gradle` file:

```gradle
dependencies {
    // JUnit
    testImplementation 'junit:junit:4.13.2'
    
    // Mockito
    testImplementation 'org.mockito:mockito-core:5.3.1'
    testImplementation 'org.mockito:mockito-inline:5.2.0'
    
    // Android Testing
    testImplementation 'androidx.arch.core:core-testing:2.2.0'
    
    // Coroutines Test
    testImplementation 'org.jetbrains.kotlinx:kotlinx-coroutines-test:1.7.3'
    
    // Optional: MockK (Kotlin-friendly mocking library)
    testImplementation 'io.mockk:mockk:1.13.5'
}
```

## Usage

1. Copy the relevant template file
2. Rename it to match your class under test (e.g., `UserViewModelTest.kt`)
3. Replace the mock dependencies with your actual dependencies
4. Uncomment and modify the test methods
5. Add your specific test cases

## Test Structure

All tests follow the Given-When-Then (Arrange-Act-Assert) pattern:

```kotlin
@Test
fun `descriptive test name`() {
    // Given (Arrange) - Set up test data and mocks
    val input = "test"
    
    // When (Act) - Execute the code under test
    val result = systemUnderTest.doSomething(input)
    
    // Then (Assert) - Verify the results
    assertEquals(expected, result)
}
```

## Running Tests

```bash
# Run all unit tests
./gradlew test

# Run specific test class
./gradlew test --tests "com.babixgo.errorgo.ExampleUnitTest"

# Run with coverage
./gradlew testDebugUnitTest jacocoTestReport
```

## Best Practices

1. **Test Naming**: Use descriptive names with backticks for better readability
2. **One Assertion**: Try to have one logical assertion per test
3. **Mocking**: Mock external dependencies, test real logic
4. **Coverage**: Aim for at least 80% code coverage
5. **Fast Tests**: Unit tests should be fast (<100ms per test)
6. **Independent**: Tests should not depend on each other
7. **Deterministic**: Tests should always produce the same result

## Additional Resources

- [Android Testing Guide](https://developer.android.com/training/testing)
- [JUnit 4 Documentation](https://junit.org/junit4/)
- [Mockito Documentation](https://site.mockito.org/)
- [Kotlin Coroutines Test](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-test/)
