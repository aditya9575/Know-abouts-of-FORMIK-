# Know-abouts-of-FORMIK-
This is a reference doc regarding how to use  -> Formik (a REACT form creation library)

Formik is a React library that makes it easy to create forms. It handles all of the boilerplate code for you, so you can focus on the form's UI and logic.

Here's a simple example of how to use Formik to create a form:

installation -> npm install formik

after installing ->

import React, { useState } from "react";
import { Formik, FormikProps } from "formik";

const MyForm = ({ initialValues }) => {
  const [values, setValues] = useState(initialValues);

  const handleChange = (e) => {
    setValues({
      ...values,
      [e.target.name]: e.target.value,
    });
  };

  const handleSubmit = (e) => {
    // Do something with the values here
    e.preventDefault();
  };

  return (
    <Formik
      initialValues={initialValues}
      onSubmit={handleSubmit}
    >
      {({ errors, touched }) => (
        <form>
          <div>
            <label htmlFor="name">Name</label>
            <input
              name="name"
              value={values.name}
              onChange={handleChange}
            />
            {errors.name && (
              <span className="invalid-feedback">
                {errors.name}
              </span>
            )}
          </div>
          <div>
            <label htmlFor="email">Email</label>
            <input
              name="email"
              value={values.email}
              onChange={handleChange}
            />
            {errors.email && (
              <span className="invalid-feedback">
                {errors.email}
              </span>
            )}
          </div>
          <button type="submit" className="btn btn-primary">Submit</button>
        </form>
      )}
    </Formik>
  );
};

export default MyForm;



(This code will create a simple form with two fields: a name field and an email field. The form will be validated, and any errors will be displayed below the fields. When the user submits the form, the handleSubmit() function will be called.)


Explanation:- 
The Formik component is used to create the form.
The initialValues prop is used to set the initial values of the form fields.
The onSubmit prop is used to handle the form submission.
The handleChange function is used to handle changes to the form fields.
The errors and touched props are used to get the errors and touched status of the form fields.
The className prop is used to style the form fields.





