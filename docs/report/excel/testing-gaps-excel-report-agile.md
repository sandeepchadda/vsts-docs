---
title: Testing Gaps Excel Report (Agile) 
description: Use the Testing Gaps report to help determine where there are deficiencies in their test plans, test configurations, and test coverage.
titleSuffix: TFS
ms.prod: devops-server
ms.technology: devops-analytics
ms.topic: reference
ms.assetid: 6f1a7509-2c47-411f-b033-ebd72b9c51d3
ms.manager: douge
ms.author: kaelliauthor: KathrynEE
ms.date: 12/30/2016
---
# Testing Gaps Excel Report (Agile)
[!INCLUDE [temp](../_shared/tfs-sharepoint-version.md)]

Teams who are responsible for testing software can use the Testing Gaps report to help determine where there are deficiencies in their test plans, test configurations, and test coverage. The Testing Gaps report provides the following five reports based on test results and builds that have been defined and run for a team project.  
  
-   **User Story Status**: Helps the team identify gaps in test coverage for each user story. This report requires that team members link test cases to user stories.  
  
-   **User Story Status by Config**: Helps the team identify gaps in test coverage for each test configuration for each user story. This report requires that team members link test cases to user stories.  
  
-   **Test Status by Area**: Helps the team identify gaps in test coverage of product areas. This report requires that team members assign test cases to product areas.  
  
-   **Tests Not Executed**: Helps the team identify test cases that have never been run for each test configuration.  
  
-   **Code Coverage**: Helps the team determine which builds and build assemblies have low or high code coverage.  
  
 The first four reports are available only when the team creates test plans and starts to run tests by using Microsoft Test Manager. For information about how to define test suites and test plans, see [Plan your tests](../../manual-test/getting-started/create-test-cases.md).  
  
> [!NOTE]
>  You can access the Testing Gaps report from the **Test Team Management** folder that is located under the **Excel Reports** folder for the team project in Team Explorer. You can access this folder only if your team project portal has been enabled and is configured to use SharePoint Products. For more information, see [Share information using the project portal](../sharepoint-dashboards/share-information-using-the-project-portal.md).  
  
 **Requirements**  
  
 To view the report, you must be assigned or belong to a group that has been assigned the **Read** permissions in SharePoint Products for the team project.  
  
 To modify or customize the report, you must be a member of the **TfsWarehouseDataReaders** security role in SQL Server Analysis Services. You must also be assigned or belong to a group that has been assigned the **Members** permissions in SharePoint Products for the team project. For more information, see [Grant Access to the Databases of the Data Warehouse for Team System](../admin/grant-permissions-to-reports.md).  
  
##  <a name="Data"></a> Data in the reports  
 The Testing Gaps reports show the cumulative count of test results for the test plans, test configurations, and test cases that are defined for a team project. All reports are based on PivotTables that access data that is stored in the data warehouse.  
  
### Test coverage of user stories  
 The User Story Status report indicates how many tests are passing or failing for each user story. It provides a horizontal bar chart that shows the count of test results for each test case and test configuration combination that the team has defined for each user story. The report presents the cumulative outcome of tests run for all test cases that are linked to user stories. The report displays results that are filtered by the following outcomes: **Passed** (green), **Failed** (red), **Never Run** (blue), or **Blocked** (yellow).  
  
 ![User Story Test Status Excel Report](_img/procg_userstorystatus.png "ProcG_UserStoryStatus")  
  
 The User Story Status by Config report presents the test results for each user story, grouped by test configuration.  
  
 The following table describes the report filters and fields that are used in the PivotTables that generate the reports that are focused on test coverage of user stories.  
  
|Filters|Fields|  
|-------------|------------|  
|-   **Team Project - Team Project Hierarchy**: Includes test results that were collected for the selected team project.<br />-   **Test Result - Iteration Hierarchy**: Includes test results that were run from test cases that were assigned to the selected iterations.<br />-   **Test Result - Area Hierarchy**: Includes test results that were run from test cases that were assigned to the selected product areas.<br />-   **Test Plan - Test Plan Name**: Includes test results that were run from test cases that belong to the selected test plans.<br />-   **Work Item Linked - Work Item Linked.Work Item Type**: Includes test results that were run from test cases that are linked to the selected work item type. The report counts test results for test cases only if they are linked to a user story.<br /><br /> **Filter specific to the User Story Status by Config report**:<br /><br /> -   **Test Suite - Test Suite Hierarchy**: Includes test results that were run from test cases that belong to the selected test suites.|<ul><li>**Test Result- Outcome**: The outcome of the test. The report uses this field to define the column labels and to filter the test results to include Passed, Failed, Blocked, or Never Run.</li><li>**(Measure) Test - Point Count Trend**: Counts the most recent version of each test result in a particular build. If a test is run multiple times against a build, the Point Count Trend counts the most recent result for that test using that build.</li><li>**Work Item Link- Title**: The title of the work item that is linked to the test case. In this report, the title of the user story is listed.</li><li>**Field specific to the User Story Status by Config report**:<br /><br /> <ul><li>**Test Configuration - Configuration Name**: The name of the test configuration to list in the report.</li></ul></li></ul>|  
  
### Test coverage by product area  
 The Test Status by Area report indicates how many test cases are passing or failing for a team project by product area. The following table describes the report filters and fields that are used in the PivotTable reports that generate the Test Status by Area report.  
  
|Filters|Fields|  
|-------------|------------|  
|-   **Team Project - Team Project Hierarchy**: Includes test results that are collected for the selected team project.<br />-   **Test Result - Iteration Hierarchy**: Includes test results that were run from test cases that were assigned to the selected iterations.<br />-   **Test Plan - Test Plan Name**: Includes test results that were run from test cases that belong to the selected test plans.|-   **Test Result- Outcome**: The outcome of the test. The report uses this field to define the column labels and to filter the test results to include Passed, Failed, Blocked, or Never Run.<br />-   **(Measure) Test - Point Count Trend**: Counts the most recent version of each test result in a particular build. If a test is run multiple times against a build, the Point Count Trend counts the most recent result for that test using that build.<br />-   **Test Result - Area Hierarchy**: The set of test results to include in the report based on the area paths that are assigned to the test cases that were run.|  
  
### Tests cases that have never run  
 The Tests Not Executed report indicates how many test cases have never run. The test cases are grouped by test configuration and test result owner. The following table describes the report filters and fields that are used in the PivotTable reports that generate the Test Status by Area report.  
  
|Filters|Fields|  
|-------------|------------|  
|-   **Team Project - Team Project Hierarchy**: Includes test results that were collected for the selected team project.<br />-   **Test Result - Iteration Hierarchy**: Includes test results that were run from test cases that were assigned to the selected iterations.<br />-   **Test Result - Area Hierarchy**: Includes test results that were run from test cases that were assigned to the selected product areas.<br />-   **Test Plan - Test Plan Name**: Includes test results that were run from test cases that belong to the selected test plans.<br />-   **Test Suite - Test Suite Hierarchy**: Includes test results that were run from test cases that belong to the selected test suites.<br />-   **Test Result- Outcome**: Includes test results with the selected outcome. The report uses this field to filter the count of test cases to include only those with an outcome of Never Run.|-   **(Measure) Test - Point Count Trend**: Counts the most recent version of each test result in a particular build. If a test case is not included in the build, it is counted as "Never Run."<br />-   **Test Configuration - Configuration Name**: The name of the test configuration to list in the report.<br />-   **Test Case- Title**: The title of the test case.<br />-   **Test Result - Owner**: The name of the team member who ran the test.|  
  
### Code Coverage  
 The Code Coverage report lists the lines of code that are covered, not covered, or only partially covered for each build and build assembly. You can use this report to determine which builds and assemblies have the lowest and highest code coverage. The following table describes the report filters and fields that are used in the PivotTables that generate the Code Coverage report.  
  
|Filters|Fields|  
|-------------|------------|  
|-   **Team Project - Team Project Hierarchy**: Includes builds that are defined for the selected team project.<br />-   **Build - Build Definition Name**: Includes builds that are associated with the selected build definitions.|-   **Build Coverage - Lines Covered**: The number of lines that are covered in the selected build.<br />-   **Build Coverage - Lines Not Covered**: The number of lines that are not covered in the selected build.<br />-   **Build Coverage - Lines Partially Covered**: The number of lines that are partially covered in the selected build. **Note:**      If multiple runs are performed against a build, the build coverage reflects the combined coverage of the runs, taking into consideration that there might be overlap in the lines covered across the runs.<br />-   **Build - Build Name**: The name of the build. Each time that a build is run, it is assigned a name that contains the build definition name as its prefix.<br />-   **Assembly - Assembly**: The assembly name against which the coverage statistics were generated.|  
  
##  <a name="RequiredActivities"></a> Required activities for monitoring testing gaps  
 For the Testing Gaps reports to be useful and accurate, the team must perform the activities that are described in the following table:  
  
|Worksheet report|Required activities|  
|----------------------|-------------------------|  
|-   User Story Status<br />-   User Story Status by Config<br />-   Test Status by Area<br />-   Tests Not Executed|-   Define test cases and test plans, and assign test cases to the test plans.<br />-   [Run tests](../../manual-test/getting-started/run-manual-tests.md), and, for manual tests, mark the results of each validation step in the test case as passed or failed.|  
|-   User Story Status<br />-   User Story Status by Config|-   Define user stories, and link test cases to user stories. The recommended link type to use is **Tested By**.|  
|-   User Story Status by Config<br />-   Tests Not Executed|-   Define test configurations, and assign to test plans or test suites. For more information, see [Test configurations: specifying test platforms](../../manual-test/test-different-configurations.md).|  
|-   User Story Status<br />-   User Story Status by Config<br />-   Test Status by Area<br />-   Tests Not Executed|-   (Optional) To support filtering, assign **Iteration** and **Area** paths to each test case. The **Test Result - Iteration Hierarchy** and **Test Result - Area Hierarchy** fields get their values from the **Iteration** and **Area** paths that are assigned to their corresponding test cases.|  
|-   User Story Status<br />-   User Story Status by Config<br />-   Test Status by Area<br />-   Tests Not Executed<br />-   Code Coverage|-   **Configure tests to gather code coverage data**. For code coverage data to appear in the report, team members must instrument tests to gather that data.|  
  
##  <a name="Updating"></a> Updating and Customizing the Report  
 You can update the Testing Gaps report by opening it in Office Excel and changing the filter options for the PivotTable report for one of the worksheets. You can customize each report to support other views, as the following table describes.  
  
|Worksheet|View|Action|  
|---------------|----------|------------|  
|-   User Story Status<br />-   User Story Status by Config<br />-   Test Status by Area<br />-   Tests Not Executed|Testing gaps for an iteration|Change the filter for **Iteration** (default=All)|  
|-   User Story Status<br />-   User Story Status by Config<br />-   Test Status by Area<br />-   Tests Not Executed|Testing gaps for a product area|Change the filter for **Area** (default=All)|  
|-   User Story Status<br />-   User Story Status by Config<br />-   Test Status by Area<br />-   Tests Not Executed|Testing gaps for a specific test plan or set of test plans|Change the filter for **Test Plan** (default=All)|  
|-   User Story Status by Config<br />-   Tests Not Executed|Testing gaps for a specific test suite|Change the filter for **Test Suite Hierarchy** (default=All)|  
|-   Code Coverage|Code coverage for a specific build definition or set of build definitions|Change the filter for **Build Definition Name** (default=All)|  
|-   User Story Status<br />-   User Story Status by Config<br />-   Test Status by Area<br />-   Tests Not Executed<br />-   Code Coverage|Testing gaps or code coverage that includes data from the most recent six, eight, or more weeks|In the Columns PivotTable Field List, add the **Date - Sets** field, and specify **@@Last 6 weeks@@** or other set|  
  
For more information about how to work with and customize PivotTable and PivotChart reports, see the following pages on the Microsoft Web site:  
 
-   [Ways to customize PivotTable reports](http://go.microsoft.com/fwlink/?LinkId=165722)    
-   [Edit or remove a workbook from Excel Services](http://go.microsoft.com/fwlink/?LinkId=165723)    
-   [Publish a workbook to Excel Services](http://go.microsoft.com/fwlink/?LinkId=165724)   
-   [Save a file to a SharePoint library or another Web location](http://go.microsoft.com/fwlink/?LinkId=165725)  
  
## Related notes
 [Test Result tables](https://msdn.microsoft.com/en-us/library/ee620635.aspx)   
 [Excel reports](excel-reports.md)
