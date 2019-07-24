# Report To Hierarchy
## Looking for assistance

### Problem Statement

Print an orgainizational hierarchy using a self-joining employee table.

### Approach

Implementation using La Vivien's ReportToHierarchy: `https://www.lavivienpost.com/build-hierarchy-tree/`

### Issue

The application this will support uses a MySQL database.  The 'report to id' (manager\_id), signifying the root, cannot be zero as this causes an error within the application thus, this is signified by setting the emp_id equal to the manager_id.  In La Vivien's solution, modifying the root to be the employee with their manager_id equal to emp_id causes La Vivien's solution to experience a stackoverflow. 

Looking for a solution to overcome this issue.

![ERD](https://github.com/robrides/ReportToHierarchy/blob/master/employee_table.png)

