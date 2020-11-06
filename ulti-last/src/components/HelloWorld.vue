<template>
  <div>
    <h3>Employee Details</h3>
    <table id="employee">
      <br />
      <br />
      <tr>
        <th>Employee_Number</th>
        <th>Employee_Name</th>
        <th>Employee_Username</th>
      </tr>
      <tr v-for="emp in details" v-bind:key="emp.Emp_id">
        <td>{{ emp.Emp_id }}</td>
        <td>{{ emp.name }}</td>
        <td>{{ emp.username }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  setup () {
    const details = [
      {
        Emp_id: '21348900',
        name: 'Jake',
        username: 'Jake3908'
      },
      {
        Emp_id: '89097567',
        name: 'Isabelle',
        username: 'Izzy70'
      },
      {
        Emp_id: '2365432',
        name: 'Mary',
        username: 'Had'
      },
      {
        Emp_id: '2343542',
        name: 'A',
        username: 'Little'
      },
      {
        Emp_id: '96455432',
        name: 'Lamb',
        username: 'Labmo'
      },
      {
        Emp_id: '23645232',
        name: 'Little',
        username: 'Marp7pi90'
      },
      {
        Emp_id: '69865432',
        name: 'Snowi',
        username: 'MarrSnowopi90'
      }
    ]
    return {
      details
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
#employee {
  font-family: "Trebuchet MS", Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 70%;
  margin-left: auto;
  margin-right: auto;
}

#employee td,
#employee th {
  border: 1px solid #ddd;
  padding: 8px;
}

#employee tr:nth-child(even) {
  background-color: #f2f2f2;
}

#employee tr:hover {
  background-color: #ddd;
}

#employee th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #dd1616;
  color: white;
}
</style>
