# contact-manager-react-appBy l
ooking at the mockup, it makes sense to have two components:

AddPersonForm: a form with the text field and Add button.

PeopleList: a list of contacts.



Let's create these components.

AddPersonForm uses state to manage the value of the text field:
function AddPersonForm() {

  const [ person, setPerson ] = useState("");



  function handleChange(e) {

    setPerson(e.target.value);

  }



  function handleSubmit(e) {

    e.preventDefault();

  }

  return (

    <form onSubmit={handleSubmit}>

    <input type="text" 

    placeholder="Add new contact" 

    onChange={handleChange} 

    value={person} />

    <button type="submit">Add</button>

    </form>

    );

}
