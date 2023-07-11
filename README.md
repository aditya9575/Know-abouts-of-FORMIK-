# Know-abouts-of-FORMIK-
This is a reference doc regarding how to use  -> Formik (a REACT form creation library)

Formik is a React library that makes it easy to create forms. It handles all of the boilerplate code for you, so you can focus on the form's UI and logic.


HERE WE ARE CREATING A SIMPLE FORM USING ------==========>>>>>>>>>>     FORMIK


steps :-

1) setup project -> npx create-react-app appName
                    (npx create-react-app formik)


2) Delete some files in the src folder -> setup tests
                                          report web vitals 
                                          logo.svg
                                          App.test.js 
                                          App.css 


3) In index.js delete ->  The Comment , Function , import statement for reportWebVitals  and save .


4) In app.js delete ->   Header section and also if preferable change the class name to lower case ->  i.e -> app

5) Now interminal -> npm install formik

6) In app.js -> import formik -> import { Formik, Form , Field } from "formik";

7) Inside div -> add 
<Formik>    
 <Form>
         
 </Form>
</Formik>

8) Now inside this Form component -> 
                                          <label> Name: </label>
                                          <Field name="name" type="text" />
                                          <br/>
                                          <label> Phone Number: </label>
                                          <Field name="phone" type="number" />



9) NOW  we have to give some initial values to our fields  -> i.e-> inside our Formik component ======> 

[NOTE -- The initial values properties used should be of the same as inside the name field in the FIELD COMPONENT for things to work ]

 <Formik initialValues={{ name:"any initial value that you want to give", phone: "initial value that you want to give"}}>
 
 </Formik>


10) To test the working till here in the terminal -> npm run start 
    (if the desired output appears on the screen we are good to go)

11) Now inside form we need our submit button so ->  inside the form component we will have a button element with type of submit   

<Form>
<button type="submit"> </button>
</Form>     

12) Till here nothing will happen when we try to submit the form but 
  
   Now for something to happen when you try to submit the form 

    * WE ADD AN  onSubmit function to our formik component -> 

  <Formik onSubmit={(values)=> {
    console.log(values);
  }}>
  
  </Formik>


  NOW if we tap onto the submit button and check our console we will have an  object with the field values of 
  name & phone number .If correct we are good to go 
  And because Formik is maintaining the state we don't need the use state hook . 


13) Now we make our password field 

        <label>Password: </label>
        <Field name="password" type="password" />
        <br/><br/>

        also add the initial values as empty string for the password field 


14) Now we make a radio button which will be used to opt for gender         
     
        <label>Gender: </label>
        <br/><br/>
        <label>Male: </label>
        <Field name="gender" value="male" type="radio" />
        <label>Female: </label>
        <Field name="gender" value="female" type="radio" />
        <br/><br/>

[Note - while using radio buttons always remember the name of the radio buttons should be the same and only values can differ]

Also assign the initial value of gender an empty string 

And if in the console after submiting the details we see the object appearing correctly we are good to go .


15) Now we add the date component 

    <label>Date: </label>
    <Field name="date" type="date" />
    <br/><br/>


Also add the initial values of the date field 

and if on submit we are able to see the correct values on the object inside the console we are good to go .


16)              NOW WE CREATE A SELECT ELEMENT -> (This is the dropdown type thing we used to opt from )

        <label>Options: </label>
        <Field name="option" as="select">
        
           <option value="1">option 1</option>
           <option value="2">option 2</option>
           <option value="3">option 3</option>
           <option value="4">option 4</option>
           <option value="5">option 5</option>

        </Field>
        <br/><br/>

        also add a initial value for option 

 Now if on refreshing we see an options tab which initiate a dropdown when being triggered on and 
 in the console we see values of option being selected appearing on submit we are good to go .     


17)  Now we add a text area element 


        <label>About: </label>
        <Field name="about" as="textarea" />
        <br/><br/>

    Also add a initial value for about 

This will give a text area element which can be used to write messages etc . 
if everything appears in the console we are good to go .


18)NOW WE CREATE A NESTED FIELDS OPTION

        <label>Social: </label>
        <br></br>
        <label>Enter Facebook username: </label>
        <Field name="social.facebook" type="text" />
        <br></br>
        <label>Enter Twitter username: </label>
        <Field name="social.twitter" type="text" />
        <br/><br/>


Also add a initial value for social i.e  -->   

social:{
      facebook:"",
      twitter:"",
       }

By using the dot operator we are now able to access the key of the the social object
and if on submit we are able to see both the values and rest of the data we are good to go . 


19)Now we store array elements 

in the place where we define initial values -> 

country :[]


now add the input fields below 

        <label>Country: </label>
        <br></br>
        <label>Enter country name: </label>
        <Field name="country[0]" type="text" />
        <br></br>
        <label>Enter country name: </label>
        <Field name="country[1]" type="text" />
        <br/><br/>


Now if on submiting we see things stored in their particular format in the console output we are good to go . 


20)Now we store field array 




