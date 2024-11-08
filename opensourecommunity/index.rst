.. _contribution_guideline:

Contribution guideline
***********************

The initial step to contribute a change or new code to a repository is to create a **Fork** of the repository. Forking is a process that duplicates the main repository, allowing the user to work on an independent copy without affecting the original codebase. 
Once the fork is created, it can be **Cloned** to the local development environment. Cloning the repository provides a local copy where the developer can implement the required modifications and test them in isolation.

After the modifications are made and verified locally, they should be committed and **Pushed** to the corresponding fork on the remote repository platform (i.e., GitHub). At this stage, it is essential to maintain a clear commit history, as this will aid reviewers in understanding the changes made. The next step is to initiate a **Pull Request (PR)** from the fork. A pull request serves as a formal request to merge the changes from the user's fork into the main repository, detailing the proposed modifications.

To streamline the review process, the pull request should have a concise yet informative title and be accompanied by a comprehensive description. This description should provide context for the changes, explain the rationale behind the decisions, and, if necessary, detail any potential implications or dependencies introduced by the new code. Where relevant, references to linked issues or enhancement requests can further clarify the necessity of the proposed change.

Once the pull request is submitted, maintainers of the main repository will review it. This review process typically involves evaluating the code against coding standards, verifying functionality, and assessing overall impact. The repository maintainers will then decide to approve, request revisions, or reject the pull request based on these criteria. Upon approval, the pull request will be merged, thereby incorporating the changes into the upstream repository.

When implementing changes, adherence to the `CoreSense Developer’s Guidelines <https://coresense.eu/wp-content/uploads/2023/11/CORESENSE_D5.1-CoreSense-ROS-Development-Guidelines.pdf>`_ is mandatory. Any code not aligning with these guidelines will be deemed non-compliant and will not be merged. Specifically, for contributions involving ROS code, compliance with ROS testing policies is required. This includes meeting the minimum requirement of unit test coverage, ensuring that all components are thoroughly tested to prevent regression and ensure robustness. Additionally, the code must pass all defined linter checks, which validate code quality, formatting, and adherence to stylistic conventions.
