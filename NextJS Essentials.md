# NextJS Essentials
## Reading Form values
```console
function handleSubmit(e) {

      e.preventDefault();
      const formData = new FormData(e.currentTarget)    // extract form data
      
      const dataObject  = Object.fromEntries(formData)  // make into an object
          //dataObject.txtName                          //or
      
      const dataValues = [...formData.values()]         // make into an array of values
      console.log (dataValues)
     
  }
  ```