# Code review checklist

This document aims to be a community and process maintained and flexible guide to test script review.
Best practice recommendations should come from the experience of script reviewers.
Pylint result of the package containing the new script(s) must to be uploaded.

## Filling instructions

It is mandatory to answer these questions at least by two reviewers (one tester and one developer) otherwise merge back to master must not be executed.
Testers shall focus on script and ims test case related reviews, while developers shall focus on the pdf report.
Remarking review tool questions is mandatory even if fulfilled!
Otherwise:
	* if a question is not relevant (specially from process-side), then please remark it.
	* if a question is okay, please accept and remark may be added.
	* if a question is not okay, please leave it empty, and remark is mandatory.


## Checklist

It is a major goal of this document that all but the most general and
best accepted guidelines should be derived from the *experience* of the code
reviewers *who use these guidelines*. This will ensure that the checklist
stays flexible, relevant and up to date.

### Script

- [ ] Is pylint rate for package higher than 9.5?
	Remark:
	
- [ ] Is the script easy to read and understand?
	Remark:
	
- [ ] Is Google docstring style used?
	Remark:
	
- [ ] Are all methods commented in a clear language?
	Remark:
	
- [ ] Are all parameters of methods are explained in docstring with intended type information?
	Remark:
	
- [ ] All public methods are provided with example calls in docsstring?
	Remark:
	
- [ ] Do comments exist and describe rationale or reasons for decisions in code instead of explaining what the code does?
	Remark:
	
- [ ] Is the script segmented enough? Are empty lines used before comment lines?
	Remark:

### Design

- [ ] Are you sure what the test purpose is about?
	Remark:
	
- [ ] Do you understand what the code does?
	Remark:
	
- [ ] Is the test case sufficiently testing the linked requirements?
	Remark:
	
- [ ] Is a realistic system usage (including worst case scenario) considered?
	Remark:
	
- [ ] Are the test input data understandable and easy to find?
	Remark:
	
- [ ] Are the test configuration parameters understandable and easy to find?
	Remark:
	
- [ ] Will you be able to modify the script to fit changing requirements or other project needs (regarding the 2 questions above)? 
	Remark:
	
- [ ] Do variables and methods have reasonable, descriptive names to understand the purpose easily even without comments?
	Remark:
	
- [ ] Are there hard-coded data that should be modifiable?
	Remark:
	
- [ ] Is the script sufficiently modular?
	Remark:
	
- [ ] Are the defined test methods (e.g equivalence partitioning aand boundary analysis) used consistently?
	Remark:
	
### Pdf report

- [ ] Is the test case's purpose clear?
	Remark:
	
- [ ] Are all necessary details (pre/postcondition, input, description, expectations) defined?
	Remark:
	
- [ ] Does precondition contains information of used power supply level, used temperature, used test equipment, used special software?
	Remark:
	
- [ ] Is it clear how to reproduce the test?
	Remark:
	
- [ ] Are all units displayed in the same format (e.g decimal places)?
	Remark:
	
- [ ] Are sw version, hardware version, fbl version filled in the beginning of report? (no dummies are allowed)
	Remark:
	

### IMS test case

- [ ] Do the pdf report's test case ID and name match with the IMS test case's ID and name?
	Remark:
	
- [ ] Is link to pdf report exist in the Content field?
	Remark:
	
- [ ] Is link to input file (excel) exist in the Test Input Values field?
	Remark:
	
- [ ] Are the Test Level, Test Type, Test Design Techniques, Test Environment fields filled in correctly?
	Remark:
	
- [ ] Is the Planned Execution Time filled in? (prediction is enough)
	Remark:

### Review tool questions

#### Requirement test specification

 - [ ] 268481: The test environment has to be defined and described. It has to be compliant with the demands of ISO 26262 (chapter 6).
	*Explanation: This means the SW Unit test has to be executed on a (simulated/real) target CPU environment under usage of the target compiler and the target compiler option set and settings. Acceptable for SW Unit testing is e.g. a direct link of Tessy to the HW target or a simulated execution on the compiler provided CPU simulator (e.g. if provided by the Windriver Workbench). Running executables on the simulator during Algo X-Checks is an acceptable substitute in addition to unit tests on a x86 platform if the tests achieve C1 coverage. It is not acceptable to have only code execution with GNU GCC compiler which executes only on x86.*
	**Remark:**
	
 - [ ] 268482: Each test case requires a description of all necessary inputs: pre-condition, test parameters and test data, description of the test event, expected results from which the decision pass/fail can be made. Each test case also requires a detailed instruction on how to execute the test.
	**Remark:**
	
 - [ ] 268556: All relevant requirements have to be linked to appropriate test cases. Relevant requirements are all planned requirements for the current sample or delivery. 
	*Explanation: It also means that the requirements have to have the quality of a requirement and have to be testable (e.g. no out of scope requirements| no 'test by review' requirements and no 'explanations' should be attempted to be tested).  Make sure that there are sufficient test cases to cover everything that is necessary. Ensure traceability by linking the test cases to the requirements. Observe that there are various tests and also reviews. Make sure to select the right one for each requirement.*
	**Remark:**
	
 - [ ] 268483: Test cases have to be specified by taking in consideration the SW Architecture and SW/Algo Design. Make sure to setup integration test cases for architecture topics and SW unit test cases for SW/Algo units.
	**Remark:**
	
 - [ ] 268143: Some test cases have to be defined to stress the functionality to at least the level of maximum realistic system usage.
	**Remark:**
	*Explanation: Worst case scenarios:
	  - Inject simultaneously Front+Side+Rear crashes and measure runtime usage.
	  - Communication: perform test cases for overloaded bus.
	  - Satellite: full data communication between satellites and ECU at undervoltage/overvoltage thresholds.*
	
	
 - [ ] 268484: Sufficient tests have to be specified to verify that all variables are initialized correctly after warm reset and cold reset.
	**Remark:**
	
 - [ ] 268144: Tests have to be specified to verify that a functionality is not exceeding the defined runtime budget agreed with the SW Architect.
	*Explanation: For Algo this is not relevant, although it is recommended that Algo will check their runtime in non-formal way before integration.*
	**Remark:**
	
 - [ ] 268727: If test code or scripts are used, the test code has to be documented and put under version management for future reproduction of the test case.
	**Remark:**
	
 - [ ] 268223: For 3rd party SW acceptance tests have to be defined.
	**Remark:**
	
 - [ ] 268406: The contents of the test specification have to cover all aspects according to the related test method e.g. equivalence partitioning and boundary analysis| C1 coverage etc.
	**Remark:**
	
 - [ ] 268407: The test end criteria and completeness criteria for the test have to be specified.
	*Explanation: The test completeness criteria shall be described for every sample phase in the specific test activity (e.g. SW requirements test) for each test set (tested function) and for each test case (expected results). *
	**Remark:**
	
 - [ ] 270172: Document here all additional findings which are not covered by any question in this review.
	*Explanation: e.g. project/product specific findings which are not covered by the checklist*
	**Remark:**
