---List the following details of each employee: employee number, last name, first name, sex, and salary.
SELECT e.emp_no, last_name, first_name, sex, salary
FROM employees AS e
JOIN salaries AS s
ON (e.emp_no = s.emp_no)

--List first name, last name, and hire date for employees who were hired in 1986
SELECT first_name, last_name, hire_date
FROM employees
WHERE extract(year from hire_date) = '1986'

--List the manager of each department with the following information: department number, department name, 
--the manager's employee number, last name, first name.
SELECT de.dept_no, d.dept_name, de.emp_no, e.last_name, e.first_name
FROM dept_emp AS de
JOIN departments AS d
ON de.dept_no = d.dept_no
JOIN employees AS e
ON de.emp_no = e.emp_no;

--List the department of each employee with the following information: 
--employee number, last name, first name, and department name.
SELECT de.emp_no, e.last_name, e.first_name, d.dept_name
FROM dept_emp AS de
JOIN employees AS e
ON de.emp_no = e.emp_no
JOIN departments AS d
ON de.dept_no = d.dept_no

--List first name, last name, and sex for employees whose first name is "Hercules" and last names begin with "B."
SELECT first_name, last_name, sex
FROM employees
WHERE first_name = 'Hercules'
AND last_name LIKE 'B%'
--AND LEFT(last_name, 1) = 'B';

--List all employees in the Sales department, including their employee number, last name, 
--first name, and department name.
SELECT de.emp_no, e.last_name, e.first_name, d.dept_name
FROM dept_emp AS de
JOIN employees AS e
ON de.emp_no = e.emp_no
JOIN departments AS d 
ON de.dept_no = d.dept_no
WHERE d.dept_name = 'Sales';

--List all employees in the Sales and Development departments, including 
--their employee number, last name, first name, and department name.
SELECT de.emp_no, e.last_name, e.first_name, d.dept_name
FROM dept_emp AS de
JOIN employees AS e
ON de.emp_no = e.emp_no
JOIN departments AS d 
ON de.dept_no = d.dept_no
--WHERE d.dept_name = 'Sales' OR d.dept_name = 'Development';
WHERE d.dept_name IN('Sales', 'Development');

--In descending order, list the frequency count of employee last names, i.e., how many employees share each last name.
SELECT last_name, count(*)
FROM employees
GROUP BY last_name
ORDER BY count(*) DESC;