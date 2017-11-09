<table>
		<tr>
			<th>员工编号</th>
			<th>员工姓名</th>
			<th>员工年龄</th>
			<th>所属部门</th>
		</tr>
		<c:forEach items="${emps}" var="e">
			<tr>
			<td>${e.empid }</td>
			<td>${e.empname }</td>
			<td>${e.empage }</td>
			<td>${e.dept.deptname }</td>
			</tr>
		</c:forEach>
	</table>
@RequestMapping(value="/list")
	public ModelAndView showEmps(){
		ModelAndView mv=new ModelAndView();
		mv.setViewName("list");
		mv.addObject("emps", this.empService.findall());
		return mv;
	}
