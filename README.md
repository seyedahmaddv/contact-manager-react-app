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

For now, we just prevent the default behavior when the form is submitted.



PeopleList received an array representing the contacts and renders a list on the page:
function PeopleList(props) {
  const arr = props.data;
  const listItems = arr.map((val, index) =>
    <li key={index}>{val}</li>
  );
  return <ul>{listItems}</ul>;
}

Now we can render our components on the page and include some initial data:

const contacts = ["James Smith", "Thomas Anderson", "Bruce Wayne"];



const el = (

  <div>

    <AddPersonForm />

    <PeopleList data={contacts} />

  </div>

);
