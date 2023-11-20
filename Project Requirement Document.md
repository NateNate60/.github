# Software Development Process
*Cloud-Based Algorithmic Trading Strategies for High-Performance Portfolios*

Chester Ornes, Dongwoo Kang, Logan Helstad, Nathan Lim, Neal Ornes, Tzu Hsuan Lee, Ya Zou

2024 Senior Software Engineering Project, Oregon State University

## Principles 

- If a team member encounters difficulties in completing their assigned tasks, it is their responsibility to proactively engage with their teammates, seeking assistance or guidance, rather than withholding information until the project's conclusion.
- All code changes, not just Pull Requests, should be reviewed by at least two team members for quality, maintainability, and adherence to coding standards.								 									
- All changes need to be developed in a separate git branch.					 								
- The Pull Request has to be reviewed by at least two team members before being	merged.
- The Pull Request needs to comply with the Definition of Done (see later) and should be linked to the corresponding work item.
- Every team member is expected to acknowledge received messages within 24 hours and, in the event of any impending inconveniences, should proactively inform all team members at least 48 hours in advance. 


## Process

Our team decided to use the Agile method for our projects because we want to make changes faster. Even though we'll work together in person sometimes, our projects need a way to work well when we're not all in the same place.
There are some other good things about using Agile:
1. Flexibility: If we run into problems during the project, we need to be able to change our plans quickly. Agile helps us do that.
2. Stakeholder Engagement: We talked to the people interested in our project, and they want to be a part of it. So, our project management needs to be able to include ideas and changes from them.

The exact process is as follows:

1. Spend 2-3 weeks on gathering requirements and analysis.
2. Spend 1 week on designing the interface of the APP.
3. Spending 85% of our time on coding and testing.
4. Spend 2-3 weeks on system and other testing such as integration test, and end-to-end test.
5. Spend 2 weeks on user acceptance testing by random sampling on the street or campus.
6. Spend 1 week changing the user interface design based on user acceptance testing feedback. 
7. Spend 5 days to check everything and make a demo to show the project partner, then deploy the product. 


## Roles

- Project Manager: Nathan Lim 
  - Responsible for overall project planning, execution, and delivery. 
  - Ensures that the project stays on schedule and within scope.
  - Manages resources and budget.
- Frontend Developers: Neal Ornes, Tzu Hsuan Lee, Ya Zou
  - Responsible for implementing the user interface based on the designs.
  - Write client-side code using web technologies (HTML, CSS, JavaScript, React).
  - Ensure a responsive and user-friendly UI. 
- Backend Developers: Dongwoo Kang, Tzu Hsuan Lee, Ya Zou 
  - Build the server-side components and architecture of the platform. 
  - Handle algorithm execution and backend APIs
  - Ensure system reliability and scalability. 
- Data Engineers:  Logan Helstad, Nathan Lim, Neal Ornes 
  - Responsible for data pipeline development and data storage infrastructure.
  - Collect, clean, and preprocess financial data for trading strategy recommendations.
  - Maintain data integrity and optimize data workflows. 
- Algorithm Optimization: Dongwoo Kang, Logan Helstad  
  - Analyze historical and real-time market data to identify trading opportunities and trends. 
  - Evaluate algorithm performance and recommend improvements. 
  - Generate insights to inform trading strategy decisions.
 
## Tooling

| Context | Tool |
| --- | --- |
| Version control | Git |
| Project management | GitHub Issues, Trello |
| Documentation | README files |
| Testing framework | Jest, cypress, Nunit, xUnit.net, `unittest`, `pytest`|
| Linting and formatting | Prettier, ESLint, Pylint |
| CI/CD | GitHub Actions |
| IDE | Visual Studio Code |
| Graphic design | Figma, Draw.io, ERDPlus |

## Definition of done

- All code changes have been reviewed, approved, and merged into the main branch (e.g., master or develop).
- Unit tests, integration tests, and end-to-end tests have been executed, and they all pass, indicating that the code changes do not have critical defects.
- If applicable, the code changes are implemented and tested in all relevant components, such as the backend, frontend, libraries, and microservices.
- The changes have not introduced any new defects or regressions in existing functionality.
- Relevant documentation, including user guides, API documentation, and internal documentation, has been updated to reflect the changes made.
- End-to-end tests have been performed to verify that all components work together seamlessly, including integrations with third-party services if applicable.
- User stories with the appropriate priority have been implemented.
- Users can use the project without needing to be specially taught how to do it by a developer.

## Release cycle

- Automated Staging Deployment: Automatically deploy to a staging environment every time a merge to the main branch occurs. This ensures that new code changes are thoroughly tested in a controlled environment.
- Scheduled Production Deployment: Deploy to the production environment on a scheduled basis to minimize disruptions to users and maintain a stable service.
- Release Frequency: Plan regular releases every three months in order to align with the OSU term schedule. This schedule provides a predictable timeframe for stakeholders and ensures a continuous delivery of new features and improvements.
- Versioning Scheme: Utilize semantic versioning (MAJOR.minor.patch) to clearly communicate the nature of each release.
- Stakeholder Involvement: Engage stakeholders, such as product managers or end-users, to prioritize features and bug fixes that determine the content of each release.
- Testing and Quality Assurance: Prior to deployment, conduct thorough testing, including functional, regression, and performance testing, to ensure the stability and reliability of the algorithm.
- Monitoring and Post-Release Evaluation: Implement robust monitoring to assess the health of the system after each release. Address any performance or reliability issues promptly.
- Iterative Feedback: Continuously gather feedback from users, fellow teammates, our professors, and our project partner to drive future changes and refinement of our algorithm.
- Documentation and Communication: Ensure that each release is well-documented to provide users and team members with clear information about changes, new features, and bug fixes.
- Continuous Improvement: As time progresses, the release cycle will become more and more clear based off of our teams individual requirements.

## Environments 

| Environment | Infrastructure | Deployment | What's it for? | Monitoring |
| -- | -- | -- | -- | -- |
| Production | AWS | Automatic deployment after new releases | This is the live environment where the application is accessible to end-users and clients, serving the purpose of executing algorithmic trading strategies for real portfolios. It is imperative to ensure high availability and performance. | We will employ monitoring tools such as Prometheus, Grafana, and New Relic to closely monitor the performance, stability, and health of the production environment. Additionally, we will implement Sentry for error tracking and alerting.|
| Staging | AWS (Render through CI/CD) | Automatic deployment of changes from the main branch after a successful pull request, or we can utilize feature flags to enable or disable specific features in production, allowing us to gradually roll out changes. | Staging is designed for testing and validating code changes before they are deployed to production. It guarantees that new features and changes do not disrupt the trading platform. This environment is vital for integration testing and validating the correctness of new features. | Sentry, Dynatrace, Datadog, AppDynamics, Ragun, Stackify Retrace, and ELK Stack (Elasticsearch, Logstash, Kibana) |
| Dev | Local | Commit to VCS (Git) | The development environment is where individual developers work on their code and conduct unit tests. It is indispensable for developing and testing new algorithmic trading strategies, features, and improvements, marking the initial phase of development.  | In most cases, monitoring may not be applicable to local development environments. Instead, developers should focus on writing unit tests and adhering to coding standards. There are a lot of testing frameworks that we can use, such as NUnit or xUnit for C#. |
