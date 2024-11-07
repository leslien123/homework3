  <!DOCTYPE html>
<!-- 
    Name: Leslie Nguyen
    File: homework1.html
    Date Created: 2024-10-14
    Date Updated: 2023-10-19
    Purpose: MIS 3371 Homework 2... Building upon the registration form.
-->
<html>
<head>
    <!-- External CSS styles -->
<link rel="stylesheet" href="mystyle2.css">


</head>
    

<div class="header">
  <img src="sonnyangellogo.png" alt="Sonny Angel" class="center">
</div>

<h1>Welcome! </h1>
<table width=100%>
 <tr>
    <td valign="bottom" align="right">Today's date: <span id="today"></span></td>
</tr>
 </table>
</body>
    <h2>SIGN UP &#129293;</h2>

    <!-- Form Starts -->
<form name="signup" id="signup" action="/hw2/homework2-thankyou.html" onSubmit="return formValidation();">

<table class="form" border="0" cellpadding="5" cellspacing="0" width="700">
<tr> <td>
    <label for="fname">First</label>, 
    <label for="miname">M</label>, 
    <label for="lname">Last:</label>
</td> <td>
    <input type="text" placeholder="Sonny" id="fname"
        name= "fname"
        maxlength="30"
        pattern="[A-Z^a-z \-']{2,}"
        oninvalid="this.setCustomValidity('Letters, apostrophes, and dashes only.')"
        oninput="this.setCustomValidity('')"
        onblur="checkFname()"
        required />
    <span class="error" id="fname-error"></span>

    <input type="text" placeholder= "I" id="miname" 
        name="miname" class="textsize1" size="1" maxlength="1"
        pattern="[A-Z^a-z']{0,1}"
        oninvalid="this.setCustomValidity('Letters only.')"
        oninput="this.setCustomValidity('')"
        onblur="checkMiname()">
    <span class="error" id="miname-error"></span>

    <input type="text" placeholder="Angel" id="lname" 
        name="lname" maxlength="30"
        pattern="[A-Z^a-z \-']{1,30}"
        oninvalid="this.setCustomValidity('Letters, apostrophes, and dashes only.')"
        oninput="this.setCustomValidity('')"
        onblur="checklname()"
        required />
    <span class="error" id="lname-error"></span>
</td> </tr> 

<tr> <td>
    <label for="phone">Phone #:</label>
</td> <td>
<input type="text" size="15" maxlength="15" id="phone" 
    name="phone"placeholder="123-456-7890"
    pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
    onblur="validatePhone()"
    required />
<span class="error" id="phone-error"></span>
</td> </tr> 

<tr> <td>
    <label for="addr1" >Address 1:</label>
</td> <td>
    <input type="text" size="20" minlength="4"maxlength="30" id="addr1" 
        name="addr1"placeholder="2222 Dream Inc."
        onblur="validateAddr1()"
        required />
  <span class="error" id="addr1-error"></span>
</td> </tr> 

<tr> <td>
    <label for="addr2">Address 2:</label>
</td> <td>
    <input type="text" size="20" maxlength="30" id="addr2"
        name="addr2" placeholder="Apt #, etc."  />
</td> </tr> 

<tr> <td>
    <label for="city">City,</label>
    <label for="state">State,</label>
    <label for="zip">Zip:</label>
</td> <td>
    <input type="text" size="10" maxlength="30" id="city" 
        name="city" placeholder="Input" required />
    <select required name="state" id="state">
                <option value=""></option>
                <option value="AL">Alabama</option>
                <option value="AK">Alaska</option>
                <option value="AZ">Arizona</option>
                <option value="AR">Arkansas</option>
                <option value="CA">California</option>
                <option value="CO">Colorado</option>
                <option value="CT">Connecticut</option>
                <option value="DE">Delaware</option>
                <option value="DC">District Of Columbia</option>
                <option value="FL">Florida</option>
                <option value="GA">Georgia</option>
                <option value="HI">Hawaii</option>
                <option value="ID">Idaho</option>
                <option value="IL">Illinois</option>
                <option value="IN">Indiana</option>
                <option value="IA">Iowa</option>
                <option value="KS">Kansas</option>
                <option value="KY">Kentucky</option>
                <option value="LA">Louisiana</option>
                <option value="ME">Maine</option>
                <option value="MD">Maryland</option>
                <option value="MA">Massachusetts</option>
                <option value="MI">Michigan</option>
                <option value="MN">Minnesota</option>
                <option value="MS">Mississippi</option>
                <option value="MO">Missouri</option>
                <option value="MT">Montana</option>
                <option value="NE">Nebraska</option>
                <option value="NV">Nevada</option>
                <option value="NH">New Hampshire</option>
                <option value="NJ">New Jersey</option>
                <option value="NM">New Mexico</option>
                <option value="NY">New York</option>
                <option value="NC">North Carolina</option>
                <option value="ND">North Dakota</option>
                <option value="OH">Ohio</option>
                <option value="OK">Oklahoma</option>
                <option value="OR">Oregon</option>
                <option value="PA">Pennsylvania</option>
                <option value="RI">Rhode Island</option>
                <option value="SC">South Carolina</option>
                <option value="SD">South Dakota</option>
                <option value="TN">Tennessee</option>
                <option value="TX">Texas</option>
                <option value="UT">Utah</option>
                <option value="VT">Vermont</option>
                <option value="VA">Virginia</option>
                <option value="WA">Washington</option>
                <option value="WV">West Virginia</option>
                <option value="WI">Wisconsin</option>
                <option value="WY">Wyoming</option>
            </select>
    <input type="text" pattern="[0-9]{5}" class="textsize5" maxlength="5" id="zip"
        size="8" name="zip" placeholder="22222"
        pattern="[0-9]{5}"
        title="Numbers only."
        onblur="validateZip()"
        required />
    <span class="error" id="zip-error"></span>
</td> </tr> 

<tr> <td>
    <label for="Country">Country:</label>
</td> <td>
<input name="Country" id="Country" 
    type="text" maxlength="30" placeholder="United States" />
</td> </tr> 

<tr> <td>
    <label for="email">Email Address:</label>
</td> <td>
    <input type="email" size="30" maxlength="40" id="email"
        name="email"
        placeholder="sonnyangel@dream.com"
        pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,20}$"
        onblur="validateEmail()"
        required />
    <span class="error" id="email-error"></span>
</td> </tr> 

<tr> <td>
    <label for="user">Username:</label>
</td> <td>
    <input type="user" size="30" maxlength="15" id="user"
        placeholder="SonnyAngel" name="firstname"
        pattern="[A-Za-z]+[A-Za-z0-9-_]{8,}"
        oninvalid="this.setCustomValidity('Invalid User ID. Enter letters, numbers, dash or underscores. 1st character must be a letter.')"
        oninput="this.setCustomValidity('')"
        onblur="validateUser()"
        required />
    <span class="error" id="user-error"></span>
</td> </tr> 

<tr> <td>
    <label for="pwd">Password:</label>
</td> <td>
    <input type="password" maxlength="15" placeholder="Enter Password" id="pwd" name="pwd" required
        pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
        title="Must contain at least one number and one uppercase and lowercase letter, minimum 8 characters or more."
            oninput="validatePassword()"
            onfocus="validatePassword()"
            onblur="validatePassword()">
        <span class="error" id="pwd-error"></span>
    <input type="password" maxlength="15" placeholder="Re-enter Password" id="pwd-confirm" name="pwd-confirm" required
        pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}" 
        title="Must contain at least one number and one uppercase and lowercase letter, minimum 8 characters or more."
            oninput="confirmPassword()"
            onfocus="confirmPassword()"
            onblur="confirmPassword()">
        <span class="error" id="pwd2-error"></span>
        <span class="pwd-message" id="pwd-error"></span>
</td> </tr>

<tr> <td>
    <label for="ssn">Social Security Number:</label>
</td> <td>
    <input type="password" id="ssn" name="ssn" 
        placeholder="123-45-6789" maxlength="11"
        title="Numbers only."
        onblur="validateSsn()"
        required />
    <span class="error" id="ssn-error"></span>
</td> </tr> 

<tr> <td>
    <label for="birthday">Birthday:</label>
</td> <td>
    <input type="date" id="dob" name="birthday"
        onblur="validateDob()"
        required />
    <span class="error" id="dob-error"></span>
</td> </tr> 

<tr> <td>
    <label for="gender">Gender:</label>
</td> <td>
    <label for="male">Male</label>
        <input type="radio" id="male" name="gender" value="Male">

    <label for="female">Female</label>
        <input type="radio" id="female" name="gender" value="Female">
    
    <label for="other">Other</label>
        <input type="radio" id="other" name="gender" value="Other">
</td> </tr> 

<tr> <td>
    <label for="collector">What series are you most excited about?</label>
</td> <td>
    <label for="animal">Animal</label>
        <input type="checkbox" id="animal" name="animal" value="Animal">

    <label for="marine">Marine</label>
        <input type="checkbox" id="marine" name="marine" value="Marine">

    <label for="sweet">Sweets</label>
        <input type="checkbox" id="sweet" name="sweet" value="Sweets">

    <label for="fruit">Fruits</label>
        <input type="checkbox" id="fruit" name="fruit" value="Fruits">

    <label for="hipper">Hippers</label>
        <input type="checkbox" id="hipper" name="hipper" value="Hippers">
    
</td> </tr> 

<tr> <td>
<label for="collector2">Rate Sonny Angels:</label>
</td> <td>
        <p>Use the slider to rate from 1 to 10:</p>

        <div class="slider-scale">
            <label for="rate-slider">(Hate)</label>
             <input type="range" id="rate-slider" name="rate-slider" min="1" max="10" value="5"
                list="increments">
            <label for="rate-slider">(Love)</label>
                
                <span id="rangedisplay"></span>
                <datalist id="increments">
                    <option value="1"></option>
                    <option value="2"></option>
                    <option value="3"></option>
                    <option value="4"></option>
                    <option value="5"></option>
                    <option value="6"></option>
                    <option value="7"></option>
                    <option value="8"></option>
                    <option value="9"></option>
                    <option value="10"></option>
                </datalist>
</td></tr>

<script>
    var slider = document.getElementById("rate-slider");
    var output = document.getElementById("rangedisplay");
    output.innerHTML = slider.value;

    slider.oninput = function() {
        output.innerHTML = this.value;
    }
</script>
        </div>
        
</td> </tr> 

<tr> <td>      
    <label for="desc">About:</label>
</td> <td>
    <textarea 
            name="desc" 
            id="desc"
            rows="4" 
            cols="50" 
            maxlength="500"
            placeholder="(Tell us about yourself)" 
            ></textarea>

            <p>By registering as a member you agree to our
                         <a href="#" style="color:dodgerblue">Privacy Policy</a> and
                         <a href="#" style="color:dodgerblue"> Terms and Conditions</a>.</p>
                                    
</td> </tr> 

<tr> <td>
    <input type="button" name="review" id="review" value="Review" onclick="reviewInput()">
    <input type="submit" value="Submit">
    <p><input type="reset" value="Clear and Start over">
</table>

    <!-- Password Match -->
<div class="pwd-message">
    <span id="msg1"></span> <br/>
    <span id="msg2"></span> <br/>
    <span id="msg3"></span> <br/>
    <span id="msg4"></span> <br/>
    <span id="msg5"></span> <br/>
    <span id="msg6"></span> <br/>
    <span id="msg7"></span> <br/>
    <span id="pwd2-error"></span> <br/>
</div>
    <center>
        <p id ="showInput"></p>
    </center>
</div>
</center>
    <!-- Footer -->
<div class="footer">
  <img src="dreamlogo.png" alt="Dream" class="center">

  <p class="center">Dream Inc. PO Box 12345, Houston, TX 22200</p>
        <p class="center">Address: 123 Dream Angel Ave, Houston, TX 22200</p>
</div>

<!-- Load external JavaScript -->
<script src="homework2-1.js"></script>

  <script>
    const d = new Date();
    let text = d.toLocaleDateString();
    document.getElementById("today").innerHTML = text;

</script>

</body>

</html>
