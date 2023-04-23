<!DOCTYPE html>
<html lang="en" dir="ltr" xmlns="http://www.w3.org/1999/html">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="{{url_for('static',filename='files/css/style1.css')}}">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.3/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
</head>
<body>
    {% if choose_file %}
    <div class="back" style="background-image: url('{{url_for('static',filename='files/css/images/kongu.jpeg')}} ');"></div>
    <form method="POST"  enctype="multipart/form-data" action="{{ url_for('home') }}">
       <div class="front">
          <input type="file" id="file" name="file" class="file">
          <input type="submit" value="save" class="save">
       </div>
    </form>
    {% else %}
    <div class="back" style="background-image: url('{{url_for('static',filename='files/css/images/kongu.jpeg')}} ');"></div>
    <div class="banner" style="background-image: url('{{url_for('static',filename='files/css/images/kongunadu.png')}} ');"></div>
    <div class="wrapper">
       <div class="display">
             {% if Names %}
               <table>
                  <thead class="name">
                    <tr>
                       <th> NAME </th>
                    </tr>
                  </thead>
                  <tbody class="mark">
                    {% for Name in Names %}
                    <tr>
                       <td>{{ Name }}</td>
                    </tr>
                    {% endfor %}
                 </tbody>
               </table>
             {% endif %}
             {% if IA_1s %}
               <table>
                 <thead class="ia_one">
                   <tr>
                      <th> IA_ONE</th>
                   </tr>
                 </thead>
                 <tbody class="mark">
                   {% for IA_1 in IA_1s %}
                    <tr>
                       <td>{{ IA_1 }}</td>
                    </tr>
                    {% endfor %}
                 </tbody>
               </table>
             {% endif %}
             {% if A1 %}
               <table>
                 <thead class="a1">
                   <tr>
                     <th>ASSI_1</th>
                   </tr>
                 </thead>
                 <tbody class="mark">
                   {% for Assi in A1 %}
                   <tr>
                      <td>{{ Assi }}</td>
                   </tr>
                     {% endfor %}
                 </tbody>
               </table>
             {% endif %}
             {% if IA_2s %}
               <table>
                 <thead class="ia_two">
                   <tr>
                     <th> IA_TWO</th>
                   </tr>
                 </thead>
                 <tbody class="mark">
                   {% for IA_2 in IA_2s %}
                   <tr>
                      <td>{{ IA_2 }}</td>
                   </tr>
                   {% endfor %}
                 </tbody>
               </table>
             {% endif %}
             {% if A2 %}
               <table>
                 <thead class="a2">
                   <tr>
                     <th>ASSI_2</th>
                   </tr>
                 </thead>
                 <tbody class="mark">
                   {% for Assign in A2 %}
                   <tr>
                      <td>{{ Assign }}</td>
                   </tr>
                   {% endfor %}
                 </tbody>
               </table>
             {% endif %}
             {% if IA_3s %}
               <table>
                 <thead class="ia_three">
                   <tr>
                     <th>IA_THREE</th>
                   </tr>
                 </thead>
                 <tbody class="mark">
                   {% for IA_3 in IA_3s %}
                   <tr>
                      <td>{{ IA_3 }}</td>
                   </tr>
                   {% endfor %}
                 </tbody>
               </table>
             {% endif %}
         </div>
      <form method="POST" action="{{ url_for('home') }}" class="container">
         <div class="box">
              <label class="box-label">Reg_no</label>
              <input  type="text" id="Reg_no" name="Reg_no" placeholder="Reg_no" class="box-input" autofocus><br>
              <label class="box-label">Name</label>
              <input type="text" id="Name" name="Name" placeholder="Name" class="box-input"><br>
              <label class="box-label">IA_1</label>
              <input type="text" id="IA_1" name="IA_1" placeholder="IA-I" class="box-input"><br>
              <label class="box-label">ASS_1</label>
              <input type="text" id="Assi" name="Assi" placeholder="ASSI-I" class="box-input"><br>
              <label class="box-label">IA_2</label>
              <input type="text" id="IA_2" name="IA_2" placeholder="IA-II" class="box-input"><br>
              <label class="box-label">ASS_2</label>
              <input type="text" id="Assign" name="Assign" placeholder="ASSI-II" class="box-input"><br>
              <label class="box-label">IA_3</label>
              <input type="text" id="IA_3" name="IA_3" placeholder="IA-III" class="box-input"><br>
              <div class="form-end">
              <input type="submit" name="submit" class="button2">
              </div>
         </div>
      </form>
   </div>

   <script>
       const Reg_noInput = document.getElementById('Reg_no');
       const NameInput   = document.getElementById('Name');
       const IA_1Input   = document.getElementById('IA_1');
       const AssiInput   = document.getElementById('Assi');
       const IA_2Input   = document.getElementById('IA_2');
       const AssignInput = document.getElementById('Assign');
       const IA_3Input   = document.getElementById('IA_3');

    Reg_noInput.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowDown') {
       event.preventDefault();
       NameInput.focus();
       }
    });
    Reg_noInput.addEventListener('keyup', (event) => {
    if (event.key === 'ArrowUp') {
       event.preventDefault();
       IA_3Input.focus();
       }
    });
    NameInput.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowDown') {
       event.preventDefault();
       IA_1Input.focus();
       }
    });
    NameInput.addEventListener('keyup', (event) => {
    if (event.key === 'ArrowUp') {
       event.preventDefault();
       Reg_noInput.focus();
       }
    });
    IA_1Input.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowDown') {
       event.preventDefault();
       AssiInput.focus();
       }
    });
    IA_1Input.addEventListener('keyup', (event) => {
    if (event.key === 'ArrowUp') {
       event.preventDefault();
       NameInput.focus();
       }
    });
    AssiInput.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowDown') {
       event.preventDefault();
       IA_2Input.focus();
       }
    });
    AssiInput.addEventListener('keyup', (event) => {
    if (event.key === 'ArrowUp') {
       event.preventDefault();
       IA_1Input.focus();
       }
    });
    IA_2Input.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowDown') {
       event.preventDefault();
       AssignInput.focus();
       }
    });
    IA_2Input.addEventListener('keyup', (event) => {
    if (event.key === 'ArrowUp') {
       event.preventDefault();
       AssiInput.focus();
       }
    });
    AssignInput.addEventListener('keyup', (event) => {
    if (event.key === 'ArrowUp') {
       event.preventDefault();
       IA_2Input.focus();
       }
    });
    AssignInput.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowDown') {
       event.preventDefault();
       IA_3Input.focus();
       }
    });
    IA_3Input.addEventListener('keyup', (event) => {
    if (event.key === 'ArrowUp') {
       event.preventDefault();
       AssignInput.focus();
       }
    });
    IA_3Input.addEventListener('keydown', (event) => {
    if (event.key === 'ArrowDown') {
       event.preventDefault();
       Reg_noInput.focus();
       }
    });
    </script>
    {% endif %}
</body>
</html>
