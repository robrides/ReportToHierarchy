# Report To Hierarchy
## ~~Looking for assistance~~ Solved

### Problem Statement

Print an orgainizational hierarchy using a self-joining employee table.

### Approach

Implementation using La Vivien's ReportToHierarchy: `https://www.lavivienpost.com/build-hierarchy-tree/`

### Issue

The application this will support uses a MySQL database.  The 'report to id' (manager\_id), signifying the root, cannot be zero as this causes an error within the application thus, this is signified by setting the emp_id equal to the manager_id.  In La Vivien's solution, modifying the root to be the employee with their manager_id equal to emp_id causes La Vivien's solution to experience a stackoverflow. 

Looking for a solution to overcome this issue.

### Resolution

A resolution to this issue was implemented which adds the following to the method 'readDataAndCreateMap()' starting directly after the opening `if` statement on line 37:

```java
if (values[0].equals(values[3])) {  
	values[3] = "0";   
}  
```

Also, if you are looking to generate the hierarchy starting at a specific employee, simply call the buildHierarchyTree method and the printHierarchyTree with `employees.get(id)` where `id` is the id of the employee with whom to begin building the tree.

Use:  
```java
buildHierarchyTree(employees.get(id));  
printHierarchyTree(employees.get(id), 0);  
```  
...insteatd of:  
```java
buildHierarchyTree(root);  
printHierarchyTree(root, 0);  
```

Hope this helps someone!

![ERD](https://github.com/robrides/ReportToHierarchy/blob/master/employee_table.png)

