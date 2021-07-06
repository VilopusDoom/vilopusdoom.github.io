---
layout: page
title: Innovation Accelerator Sample Website Profile Delivery Option
permalink: /iatestbed/
---


<form action="https://getform.io/f/f32246bf-48a3-44b4-9ab5-94db91f9f839" method="POST">

  <label for="name">Please Enter Your Name</label><br>
  <input type="text" name="name" id="name" placeholder="Full Name" required><br>
  <label for="email">Please Enter Your E-mail Address</label><br>
  <input type="email" name="email" id="email" placeholder="name@address.domain" required><br>
  <label for="phone">Please Enter Your Phone Number</label><br>
  <input type="tel" id="phone" name="phone" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" placeholder="345-621-7890"><br>
  
  Please enter your age: <br>
  <input type="radio" id="17-" name="age" value="17 and under">
  <label for="17-">17 and under</label><br>
  <input type="radio" id="1834" name="age" value="18-34">
  <label for="1834">18-34</label><br>
  <input type="radio" id="3550" name="age" value="35-50">
  <label for="3550">35-50</label><br>
  <input type="radio" id="5164" name="age" value="51-64">
  <label for="5164">51-64</label><br>
  <input type="radio" id="65" name="age" value="65+">
  <label for="65">65+</label><br>
  
  <label for="numpeople">How many people are in your household?</label><br>
  <input type="number" id="numpeople" name="numpeople" min="1" max="25" placeholder="1"><br>
  
  
  Select any food related allergens:<br>
  <div>
  <input type="checkbox" id="nut" name="allergy[]" value="Tree Nut"
         >
  <label for="nut">Tree Nut</label>
</div>
  
  <div>
  <input type="checkbox" id="dairy" name="allergy[]" value="Dairy"
         >
  <label for="dairy">Dairy</label>
</div>
  
<div>
  <input type="checkbox" id="gluten" name="allergy[]" value="Gluten">
  <label for="gluten">Gluten</label>
</div>
  
  <div>
  <input type="checkbox" id="shellfish" name="allergy[]" value="Shellfish"
         >
  <label for="shellfish">Shellfish</label>
</div>
  
  <div>
  <input type="checkbox" id="other-allergy" name="other-allergy"
         >
  <label for="other-allergy">Other:</label><input type="text" id="allergy[]" name="other-desc-allergy">
</div>
  
  <br>
  Select any dietary restrictions:<br>
  <div>
  <input type="checkbox" id="vegan" name="restr[]" value="Vegan"
         >
  <label for="vegan">Vegan</label>
</div>
  
  <div>
  <input type="checkbox" id="vegetarian" name="restr[]" value="Vegetarian"
         >
  <label for="vegetarian">Vegetarian</label>
</div>
  
<div>
  <input type="checkbox" id="halal" name="restr[]" value="Halal">
  <label for="halal">Halal</label>
</div>
  
  <div>
  <input type="checkbox" id="kosher" name="restr[]" value="Kosher"
         >
  <label for="kosher">Kosher</label>
</div>
  
  <div>
  <input type="checkbox" id="other-rest" name="other-rest"
         >
  <label for="other-rest">Other:</label><input type="text" id="restr[]" name="other-desc-rest">
</div>
  
  <br>
  <label for="last-requests">Do you have any other specific requests?</label><br>
  <input type="text" id="last-requests" name="last-requests"><br>
  <button type="submit">Submit</button>

</form>
        
