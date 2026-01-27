## Stateless unit testing using examples, tables, and properties

In this project, we'll use [jqwik](https://jqwik.net/) for practicing these styles of unit testing.


## Individual project

- Discuss your approach with your classmates, TA, and instructor
- Maintain and submit your own repository


## Project description

Fix the various TODO items until all tests pass, including those you are about to add.

    ❯ grep -r TODO src


## Nonfunctional requirements

For full credit, the various palindrome checkers should meet the following nonfunctional requirements (NFRs):

- constant additional space (O(1)) preferred 
- up to arg.length / 2 additional space acceptable
- as DRY (don't repeat yourself) as possible, i.e., the methods should call each other as appropriate

In addition, the project must meet these NFRs:

- multiple git commits
- unchanged Gradle-based project structure and dependencies (you may add additional useful dependencies)
- compiles and runs (main and tests) using Gradle


## Running the main program

The main program checks whether the command-line arguments form a palindrome, defined as a string that reads the same way forward and backward, possibly considering or ignoring case and/or spaces. 
When inspecting the main method, you'll see that it concatenates the command-line arguments to a single string with spaces in between.

    ❯ ./gradlew run --args="Rad a r"
    checking Rad a r
    Rad a r is not a palindrome.
    Rad a r is not a case-sensitive palindrome.
    Rad a r is a case-insensitive palindrome when ignoring spaces.


## Running the tests

You can run all the tests

    ❯ ./gradlew test

or a specific test or single test method, which is recommended while you're focusing on each specific part of the project

    ❯ ./gradlew test --tests TestPalindromeExamples

    ❯ ./gradlew test --tests TestPalindromeExamples.testRadar
    

You can generate the coverage report using

    ❯ ./gradlew jacocoTestReport


## Written part

Succinctly answer the following questions in a separate document called Answer.md in this repository.

- Which of the NFRs listed above are dynamic or static, respectively?
- Why is space performance important for a predicate like `isPalindrome`?
- To what extent does the result of invoking one of these predicates depend on prior invocations?
- Accordingly, what would be a relatively straightforward way to improve their performance?
- What is an advantage of data-driven testing over example-based testing?
- What is an advantage of property-based testing over example-based and data-driven testing?
- Briefly discuss the pros and cons of a generate-and-check-based property as compared to a property based on a generator that generates test data more directly, such as the ones listed below under extra credit?


## Grading

- 2 NFRs
- 1.5 three palindrome checker methods
- 0.5 invoke additional two checkers in main
- 1.5 additional example-based tests
- 1.5 additional tables for data-driven tests
- 1 additional properties
- 2 written part
- 10 TOTAL


## Extra credit

- 0.2 add a working CI status badge for your project
- 0.5 for an efficient generator of case-sensitive palindromes up to a given length
- 0.5 for an efficient generator of case-insensitive palindromes up to a given length
- 0.5 for an efficient generator of case/space-insensitive palindromes up to a given length
- 0.5 for an efficient generator of non-palindromes up to a given length (easiest)
