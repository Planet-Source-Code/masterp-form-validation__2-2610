<div align="center">

## Form Validation


</div>

### Description

This code validates the information entered into a form using javascript. It validates the name, location, date, and e-mail address.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[masterp](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/masterp.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |
**Category**       |[Forms Validation Processing](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/forms-validation-processing__2-76.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/masterp-form-validation__2-2610/archive/master.zip)





### Source Code

```
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=windows-1252">
<meta name="description" content="">
<meta name="GENERATOR" content="">
<meta name="keywords" content="">
<meta name="ProgId" content="">
<title> Registration</title>
<link rel="stylesheet" type="text/css" href="style.css">
<script>
window.focus()
function validateForm(){
 var sFirstname = document.forms[0].first.value
 var sLastname = document.forms[0].last.value
 var badChar = "!@#$%^&*()-=+[]{}\\|;:'\",./<>_`~?"
 var badNum = "345678"
 var badNum2 = "12345678"
 var sEmail = document.forms[0].email.value
 var bGender1 = document.forms[0].gender[0].checked
 var bGender2 = document.forms[0].gender[1].checked
 var sUsername = document.forms[0].username.value
 var sPassword = document.forms[0].pass1.value
 var sPassword2 = document.forms[0].pass2.value
 var iMonth = document.forms[0].month.selectedIndex
 var iDay = document.forms[0].day.selectedIndex
 var iYear = document.forms[0].year.value
 var sState = document.forms[0].State.selectedIndex
 var sCountry = document.forms[0].Country.selectedIndex
 if (sUsername.length < 1) {
   alert("You must supply your username!")
   return false
 }
 for(var i = 0; i <= sUsername.length-1; i ++){
   for(var j = 0; j <= badChar.length-1; j++){
     if (sUsername.charAt(i)==badChar.charAt(j)){
       alert("Your username contains an invalid character!\n\nUsernames may only contain letters and numbers\n no spaces, special characters or symbols allowed.")
       return false
     }
   }
 }
 if ((sUsername.length < 4) || (sUsername.length > 14)){
   alert("Your username must be between 4 and 14 characters!")
   return false
 }
 if (sPassword != sPassword2) {
   alert("Your passwords don't match!")
   return false
 }
 if ((sPassword.length < 1) ||(sPassword2.length < 1)){
   alert("Your password is required!")
   return false
 }
 if ((sPassword.length < 4) || (sPassword.length > 14)){
   alert("Your password must be between 4 and 14 characters!")
   return false
 }
 if (sFirstname.length < 1) {
   alert("Your first name is required!")
   return false
 }
 if(sLastname.length < 1){
   alert("Your last name is required!")
   return false
 }
 for(var j = 0; j <= badChar.length - 1; j++) {
   if (sFirstname.charAt(0) == badChar.charAt(j)){
	 alert("Your first name cannot begin with an invalid character!")
	 return false
   }
 }
 for(var j = 0; j <= badChar.length - 1; j++) {
   if (sLastname.charAt(0) == badChar.charAt(j)){
	 alert("Your last name cannot begin with an invalid character!")
	 return false
   }
 }
 if (!bGender1 && !bGender2){
   alert("You need to choose a gender!")
   return false
 }
 if(iMonth == 0 || iDay == 0 ){
   alert("You need to put in your Birthdate!")
   return false
 }
 if(iYear.length < 1){
   alert("You need to put your Birth Year!")
   return false
 }
 if(iYear.length < 4){
   alert("You need to put your Birth Year!")
   return false
 }
 if (iYear.charAt(0) == 1){
   if (iYear.charAt(0) == 1 && iYear.charAt(1) != 9){
     alert("Your birth year must be between 1900 and 2000!")
     return false
   }
 }
 if (iYear.charAt(0) == 2){
   if (iYear.charAt(0) == 2 && iYear.charAt(1) != 0){
     alert("Your birth year must be between 1900 and 2000!")
     return false
   }
 }
 if (sEmail.length < 1) {
   alert("You must supply a valid e-mail address!")
   return false
 }
 if (sEmail.length > 1) {
   if (sEmail.indexOf("@") == -1) {
     alert("You did not type a valid e-mail address!")
     return false
   }
 }
 if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(Form.sEmail.value)){
   return true
 }
 Else{
   alert("Invalid E-mail Address! Please re-enter.")
   return false
 }
 if((sState == 0 ) && (sCountry == 0) ){
   alert("You must select either a state or a country where you are from!")
   return false
 }
}
</script>
</head>
<body bgcolor="#ffffff" text="#000000">
<table border="0" width="100%" cellspacing="0" cellpadding="0">
<td align=center>
  <!--<p align="left"><H2>Register Now</p>-->
  <form action="register2.asp" method="post" onSubmit="return validateForm()">
<table border=1 bordercolor=black cellspacing=0 cellpadding=1 width=490 bgcolor="#EFEFEF">
 <tr CLASS="CAL">
  <td colspan=1>Registration</td>
 </tr>
 <tr>
 <td align=center>
  <table border=0 cellspacing=0 cellpadding=2 width=460 bgcolor="#EFEFEF">
   <tr><td colspan=4><IMG src="img/pixel.gif" width="1" height="1" border="0"></td></tr>
   <tr CLASS="Data"><td colspan=4>Account Information</td></tr>
   <tr><td colspan=4><IMG src="img/pixel.gif" width="1" height="1" border="0"></td></tr>
   <tr><td width=120><b>Username: </b></td>
	 <td><input type="text" name="username" CLASS="Input" size=20 maxlength=15>&nbsp;</td>
	 <td Class="Small" colspan=2>Begin with a letter, and use only letters (a-z), numbers (0-9), the underscore (_), and no spaces.</td>
   </tr>
   <tr><td><b>Password:</b></td>
	 <td><input type="password" name="pass1" CLASS="Input" size=20 maxchars=14></td>
   </tr>
   <tr><td><b>Password (again): </b></td>
	 <td><input type="password" name="pass2" CLASS="Input" size=20 maxchars=14></td>
   </tr>
   <tr><td><b>Secret Question: </b></td>
	 <td colspan=2><input type="text" name="question" CLASS="Input" size=20 maxchars=50></td>
   </tr>
   <tr><td><b>Answer: </b></td>
	 <td><input type="text" name="answer" CLASS="Input" size=20 maxchars=40></td>
   </tr>
   <tr><td><b>Notify Me: </b></td>
	 <td><input type="radio" name="notify" value="Yes" checked >Yes &nbsp;&nbsp;&nbsp;&nbsp;
	  <input type="radio" name="notify" value="No" >No</td>
     <td Class="Small" colspan=2>Check yes if you would like to be notified when you have new messages.</td>
   <tr>
   <tr><td colspan=4><IMG src="img/pixel.gif" width="1" height="1" border="0"></td></tr>
   <tr CLASS="Data"><td colspan=4>Personal Profile</td></tr>
   <tr><td colspan=4><IMG src="img/pixel.gif" width="1" height="1" border="0"></td></tr>
   <tr><td><b>First Name: </b></td>
	 <td><input type="text" name="first" CLASS="Input" size=20 maxchars=15></td>
   </tr>
   <tr><td><b>Last Name: </b></td>
	 <td><input type="text" name="last" CLASS="Input" size=20 maxchars=15></td>
   </tr>
   <tr><td><b>Gender: </b></td>
	 <td><input type="radio" name="gender" value="male" checked >Male &nbsp;&nbsp;&nbsp;&nbsp;
	  <input type="radio" name="gender" value="female" >Female</td>
   <tr>
	<td><b>Birthday: </b></td>
	<td>
	<select name="month">
	<option value="0">Month<option value="1">January<option value="2">February
	<option value="3">March<option value="4">April<option value="5">May
	<option value="6">June<option value="7">July<option value="8">August
	<option value="9">September<option value="10">October<option value="11">November
	<option value="12">December</select><nobr>
	<select name="day" >
	<option value="0">Day<option value="1">1<option value="2">2<option value="3">3
	<option value="4">4<option value="5">5<option value="6">6<option value="7">7
	<option value="8">8<option value="9">9<option value="10">10<option value="11">11
	<option value="12">12<option value="13">13<option value="14">14<option value="15">15
	<option value="16">16<option value="17">17<option value="18">18<option value="19">19
	<option value="20">20<option value="21">21<option value="22">22<option value="23">23
	<option value="24">24<option value="25">25<option value="26">26<option value="27">27
	<option value="28">28<option value="29">29<option value="30">30<option value="31">31
	</select></td>
	<td colspan=2><input type="text" name="year" value="" size="4" maxlength="4" CLASS="Input">&nbsp;Ex: June 15 1979</td>
   </tr>
   <tr><td><b>Email<nobr> Address: </b></td>
	 <td><input type="text" name="email" CLASS="Input" size=20 maxchars=50></td>
   </tr>
   <tr><td><b>State </b></td>
	 <td colspan=2><SELECT NAME="State" tabindex=11 ALIGN=MIDDLE onChange="document.forms[0].Country.selectedIndex=0">
	 <option value="none">(USA Residents: Select a state)
     <option value=AL>Alabama
     <option value=AK>Alaska
     <option value=AZ>Arizona
     <option value=AR>Arkansas
     <option value=CA>California
     <option value=CO>Colorado
     <option value=CT>Connecticut
     <option value=DE>Delaware
     <option value=DC>District of Columbia
     <option value=FL>Florida
     <option value=GA>Georgia
     <option value=HI>Hawaii
     <option value=ID>Idaho
     <option value=IL>Illinois
     <option value=IN>Indiana
     <option value=IA>Iowa
     <option value=KS>Kansas
     <option value=KY>Kentucky
     <option value=LA>Louisiana
     <option value=ME>Maine
     <option value=MD>Maryland
     <option value=MA>Massachusetts
     <option value=MI>Michigan
     <option value=MN>Minnesota
     <option value=MS>Mississippi
     <option value=MO>Missouri
     <option value=MT>Montana
     <option value=NE>Nebraska
     <option value=NV>Nevada
     <option value=NH>New Hampshire
     <option value=NJ>New Jersey
     <option value=NM>New Mexico
     <option value=NY>New York
     <option value=NC>North Carolina
     <option value=ND>North Dakota
     <option value=OH>Ohio
     <option value=OK>Oklahoma
     <option value=OR>Oregon
     <option value=PA>Pennsylvania
     <option value=RI>Rhode Island
     <option value=SC>South Carolina
     <option value=SD>South Dakota
     <option value=TN>Tennessee
     <option value=TX>Texas
     <option value=UT>Utah
     <option value=VT>Vermont
     <option value=VA>Virginia
     <option value=WA>Washington
     <option value=WV>West Virginia
     <option value=WI>Wisconsin
     <option value=WY>Wyoming
     </SELECT></td>
   </tr>
   <tr><td><b>Country</b></td>
	 <td colspan=2><select tabindex=12 name="Country" onChange="document.forms[0].State.selectedIndex=0">
     <option value="none">(Only select a country if outside USA)
     <option value=AF>Afghanistan
     <option value=AI>Albania
     <option value=AG>Algeria
     <option value=AS>American Samoa
     <option value=AN>Andorra
     <option value=AO>Angola
     <option value=AA>Anguilla
     <option value=AC>Antarctica
     <option value=AB>Antigua and Barbuda
     <option value=AT>Argentina
     <option value=AM>Armenia
     <option value=AU>Aruba
     <option value=AW>Australia
     <option value=AX>Austria
     <option value=AY>Azerbaijan
     <option value=BA>Bahamas
     <option value=BH>Bahrain
     <option value=BG>Bangladesh
     <option value=BB>Barbados
     <option value=BL>Belarus
     <option value=BM>Belgium
     <option value=BZ>Belize
     <option value=BN>Benin
     <option value=BR>Bermuda
     <option value=BT>Bhutan
     <option value=BV>Bolivia
     <option value=BS>Bosnia and Herzegovina
     <option value=BW>Botswana
     <option value=BI>Bouvet Island
     <option value=BX>Brazil
     <option value=BO>British Indian Ocean Territory
     <option value=BY>British Virgin Islands
     <option value=BU>Brunei
     <option value=BP>Bulgaria
     <option value=BF>Burkina Faso
     <option value=BD>Burundi
     <option value=CB>Cambodia
     <option value=CM>Cameroon
     <option value=CN>Canada
     <option value=CV>Cape Verde
     <option value=CI>Cayman Islands
     <option value=CR>Central African Republic
     <option value=CH>Chad
     <option value=CL>Chile
     <option value=CX>China
     <option value=CS>Christmas Island
     <option value=CC>Cocos Islands
     <option value=CW>Colombia
     <option value=CE>Comoros
     <option value=CG>Congo
     <option value=CK>Cook Islands
     <option value=CD>Costa Rica
     <option value=CQ>Croatia
     <option value=CU>Cuba
     <option value=CY>Cyprus
     <option value=CZ>Czech Republic
     <option value=DN>Denmark
     <option value=DJ>Djibouti
     <option value=DO>Dominica
     <option value=DR>Dominican Republic
     <option value=EA>East Timor
     <option value=EC>Ecuador
     <option value=EG>Egypt
     <option value=EL>El Salvador
     <option value=EQ>Equatorial Guinea
     <option value=ER>Eritrea
     <option value=ES>Estonia
     <option value=ET>Ethiopia
     <option value=FA>Falkland Islands
     <option value=FO>Faroe Islands
     <option value=FI>Fiji
     <option value=FN>Finland
     <option value=FR>France
     <option value=FG>French Guiana
     <option value=FP>French Polynesia
     <option value=FS>French Southern Territories
     <option value=GB>Gabon
     <option value=GM>Gambia
     <option value=GO>Georgia
     <option value=GE>Germany
     <option value=GH>Ghana
     <option value=GI>Gibraltar
     <option value=GR>Greece
     <option value=GL>Greenland
     <option value=GN>Grenada
     <option value=GU>Guadeloupe
     <option value=GX>Guam
     <option value=GT>Guatemala
     <option value=GV>Guinea
     <option value=GS>Guinea-Bissau
     <option value=GY>Guyana
     <option value=HA>Haiti
     <option value=HE>Heard and McDonald Islands
     <option value=HO>Honduras
     <option value=HK>Hong Kong
     <option value=HU>Hungary
     <option value=IC>Iceland
     <option value=II>India
     <option value=IO>Indonesia
     <option value=IR>Iran
     <option value=IQ>Iraq
     <option value=IE>Ireland
     <option value=IS>Israel
     <option value=IT>Italy
     <option value=IV>Ivory Coast
     <option value=JA>Jamaica
     <option value=JP>Japan
     <option value=JO>Jordan
     <option value=KA>Kazakhstan
     <option value=KE>Kenya
     <option value=KI>Kiribati
     <option value=KN>Korea, North
     <option value=KO>Korea, South
     <option value=KU>Kuwait
     <option value=KG>Kyrgyzstan
     <option value=LO>Laos
     <option value=LT>Latvia
     <option value=LE>Lebanon
     <option value=LS>Lesotho
     <option value=LI>Liberia
     <option value=LB>Libya
     <option value=LC>Liechtenstein
     <option value=LH>Lithuania
     <option value=LU>Luxembourg
     <option value=MU>Macau
     <option value=MC>Macedonia, Frmr Yugo. Rep. of
     <option value=MG>Madagascar
     <option value=MW>Malawi
     <option value=ML>Malaysia
     <option value=MV>Maldives
     <option value=MM>Mali
     <option value=MB>Malta
     <option value=MF>Marshall Islands
     <option value=MQ>Martinique
     <option value=MH>Mauritania
     <option value=MJ>Mauritius
     <option value=MK>Mayotte
     <option value=MX>Mexico
     <option value=MP>Micronesia, Federated States of
     <option value=NB>Moldova
     <option value=NF>Monaco
     <option value=NN>Mongolia
     <option value=MR>Montserrat
     <option value=NO>Morocco
     <option value=MZ>Mozambique
     <option value=MY>Myanmar
     <option value=NA>Namibia
     <option value=NU>Nauru
     <option value=NP>Nepal
     <option value=NT>Netherlands
     <option value=NL>Netherlands Antilles
     <option value=NW>New Caledonia
     <option value=NZ>New Zealand
     <option value=NG>Nicaragua
     <option value=NR>Niger
     <option value=NI>Nigeria
     <option value=NX>Niue
     <option value=NK>Norfolk Island
     <option value=NS>Northern Mariana Islands
     <option value=NQ>Norway
     <option value=OM>Oman
     <option value=OO>Other (please specify)
     <option value=PK>Pakistan
     <option value=PL>Palau
     <option value=PN>Panama
     <option value=PP>Papua New Guinea
     <option value=PR>Paraguay
     <option value=PE>Peru
     <option value=PH>Philippines
     <option value=PT>Pitcairn Island
     <option value=PO>Poland
     <option value=PG>Portugal
     <option value=PU>Puerto Rico
     <option value=QA>Qatar
     <option value=RE>Reunion
     <option value=RO>Romania
     <option value=RU>Russia
     <option value=RW>Rwanda
     <option value=SG>S. Georgia and S. Sandwich Isls.
     <option value=SK>Saint Kitts & Nevis
     <option value=SL>Saint Lucia
     <option value=SV>Saint Vincent and The Grenadines
     <option value=SO>Samoa
     <option value=SM>San Marino
     <option value=ST>Sao Tome and Principe
     <option value=SA>Saudi Arabia
     <option value=SN>Senegal
     <option value=SY>Seychelles
     <option value=SI>Sierra Leone
     <option value=SP>Singapore
     <option value=SJ>Slovakia
     <option value=SX>Slovenia
     <option value=SS>Somalia
     <option value=SF>South Africa
     <option value=SB>Spain
     <option value=SR>Sri Lanka
     <option value=SE>St. Helena
     <option value=SH>St. Pierre and Miquelon
     <option value=SU>Sudan
     <option value=SQ>Suriname
     <option value=JM>Svalbard and Jan Mayen Islands
     <option value=WZ>Swaziland
     <option value=SZ>Sweden
     <option value=SW>Switzerland
     <option value=YR>Syria
     <option value=TA>Taiwan
     <option value=TJ>Tajikistan
     <option value=TZ>Tanzania
     <option value=TH>Thailand
     <option value=TO>Togo
     <option value=TK>Tokelau
     <option value=TG>Tonga
     <option value=TR>Trinidad and Tobago
     <option value=TU>Tunisia
     <option value=TY>Turkey
     <option value=TT>Turkmenistan
     <option value=TC>Turks and Caicos Islands
     <option value=TV>Tuvalu
     <option value=UM>U.S. Minor Outlying Islands
     <option value=UG>Uganda
     <option value=UE>Ukraine
     <option value=UA>United Arab Emirates
     <option value=UK>United Kingdom
     <option value=UR>Uruguay
     <option value=UZ>Uzbekistan
     <option value=VN>Vanuatu
     <option value=VC>Vatican City
     <option value=VZ>Venezuela
     <option value=VM>Vietnam
     <option value=VG>Virgin Islands
     <option value=WF>Wallis and Futuna Islands
     <option value=WE>Western Sahara
     <option value=YE>Yemen
     <option value=YM>Yugoslavia (Former)
     <option value=ZA>Zaire
     <option value=ZM>Zambia
     <option value=ZB>Zimbabwe
     </select></td>
   </tr>
  </table>
 </td></tr>
</table>
	<p>
	<input type="submit" value="Submit Registration"> <input type="Reset" value="Start Over">
  </form>
  </td></tr>
</table>
</body>
</html>
```

