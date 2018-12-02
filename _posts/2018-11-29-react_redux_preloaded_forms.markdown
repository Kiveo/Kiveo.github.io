---
layout: post
title: "React Redux Preloaded forms"
date:       2018-11-29 00:30:00 +0000
permalink:  react_redux_preloaded_forms
excerpt: "Tutorials online often speak about Reactjs forms. One of the first things they will lead one to do is create a 'controlled' form. So, we are going to refresh some of the basic concepts surrounding react forms and redux integration. That said, our focus is going to be a bit further down the rabbit hole: preloaded form data. This is especially useful for an edit or update page."
---
 
Tutorials online often speak about Reactjs forms. One of the first things they will lead one to do is create a 'controlled' form. So, we are going to refresh some of the basic concepts surrounding react forms and redux integration. That said, our focus is going to be a bit further down the rabbit hole: preloaded form data. This is especially useful for an edit or update page.

Here is a sample update form:
![Edit Form](https://lh3.googleusercontent.com/9eI9Qd5r8UlD5Ech5Ke_svufIhslZYg1ewjWPaUd_x0w_7YvyOYgBDrOGOCLDVDe4acmij-w5One7pHMCUiHUygQY2JrJs98d47j95Z6goEL9-oGHv4EmJJ1cG2b4_h8s2SlUj459lBx8GGnWDd-zj3et4uWhJ8ODjoOpSzElICJ4fFvAgZ_iTA9xB_tF9NxwuJuIolbnIuo3fZESaJjNXh5cnJrBjjgJTwJGxpAIsDIkxiWP4lGiE13TRUiG_zJemdOx-l_uNyJLRAhkQt776wjJr-HPBNAn0BRelhs9tIuGeA47szGyUFm4lT9T5xgAAidOIAzS3watwRJBI6QhfBjthxsYbRujCbWfbngWDs7vCg4T_ukiv6MnFR1gLTLHbQ5yXLkCfTX_L9RyjZweIjig0kbm33E31a0VuMtJR548BG0d8bkLk7cPuspB5mP8Tbca_LNnRFia7YN75PU3WKOowsd0wd3Ot1rNHDx3mO6KyOyT2yhUgQovLAm_TAVz6U8rYl0OODKcp53wQEaPKOyLUWf2Px2OpKYh3OX5paMI15i0as2kj-LuK0M3vvnRMo6LayFZw2ioEBPSIZZG0rys0QgNN0pNC138uJfR5Q2AH38XBefYrhQM7XE2UljKo4S7yq0_ErstSN208gOadco=w1330-h760-no)

A quick review: a *controlled form* is generally considered a form whose input fields are monitored and mirrored into the state of the component. Since we are using Redux, our state is not local to the component, it's usually in the single-state store. The concept remains. An *uncontrolled form* is a form where changes to the input field do not dynamically update the component/store's state. We do not 'control' the state with an uncontrolled form. 

We control input fields by adding listeners, such as 'onChange'. Then, we use the onChange listener to trigger some function, such as 'handleOnChange()'. Finally, within that function, we update the state using either React's setState() or sending a dispatch via Redux. I will not cover the specifics here because our focus is more about pre-loaded forms using React & Redux, than forms in general.

Alright, so we've reviewed the basic definition and process of controlling/not controlling forms in React Redux. Now the big question: How do we load previously stored data from the Redux store into a form? Presuming we want to use "defaultValue", there is something to note. If we try to both control our form (which requires using the form property 'value') and use default values loaded in from our store, React will give us an error. Apparently, we are not allowed to use both 'defaultValue' and 'value' properties concurrently. 

Ok. That's a bit of a nuisance. We definitely want a default value so that if the user inputs nothing they keep their previous data. We also need the ability to take whatever input they did alter to trigger an action-dispatch-store change in Redux. Ok, it's time to harken back to our intro: controlled and uncontrolled states. Since we are speaking about an edit/update form, do we really need a controlled form?

Well, no. We are still able to submit data with an uncontrolled form (non-javascript sites do it everyday, afterall). In fact, one of the major reasons we use controlled forms is to ensure the state is up to date. That's fine and dandy, but if a user is editing or updating an entry, they may well not want any changes saved immediately. More to the point: the state *should* remain the same *until* a user submits an edit, so that we can provide the user the current state (via a rendering of it or the default entries of the form).  

Alright, so let's use an uncontrolled form! Thus, we do not use value and onChange(). Instead, we are going to only use the defaultValue property of the form. The appropriate store data is provided as the default value. Assuming you're using Redux, we still map our dispatch (something like 'updateThing') and call it within our submit handler.  

Here is a sample uncontrolled form, which uses default values:
~~~~
   render() {
    const {name, gender, location} = this.props.person;
    
    return(
      <div>
        <form className="PersonForm" onSubmit={this.handleOnSubmit}>
          <h1>Edit Person Details</h1>
          
          <label>Person's Name</label>
          <input type="text" name="name" defaultValue={name} /> 
          <label>Person's Gender</label>
          <input type="text" name="gender" defaultValue={gender} />
          <label>Person's Location</label>
          <input type="text" name="location" defaultValue={location} />

          <input type="submit" />
        </form>
      </div>
~~~~

Depending on how your project is set up, you can mapStateToProps or pass props to this form component, but the idea remains the same. We use the current object's state (person in the above example) to populate data into our fields. The user can edit that data and submit. The onSubmit triggers a function that handles form inputs and ultimately sends a Redux dispatch to update the store state.  

This wraps up how we can use an uncontrolled form to preload form data in React Redux. 

As always,  
Coffee and Code On, friends!


*SOURCES:*  
[React Forms](https://reactjs.org/docs/forms.html)  

[Uncontrolled Forms](https://reactjs.org/docs/uncontrolled-components.html)

*Notes: There are other methods out there, such as leveraging the libraries of Redux-Forms and React Redux Form, so I encourage the reader do to their own research and determine what works best for them.*