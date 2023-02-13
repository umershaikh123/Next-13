# React important concepts


## objects in useState Hook

```
const [position, setPosition] = useState({ x: 0, y: 0 });
const [artists, setArtists] = useState([]); // array

<!-- Add objects to array -->
setArtists([
  ...artists,
  { id: nextId++, name: name }
]);

<!-- Nested object -->
const [person, setPerson] = useState({
  name: 'Niki de Saint Phalle',
  artwork: {
    title: 'Blue Nana',
    city: 'Hamburg',
    image: 'https://i.imgur.com/Sd1AgUOm.jpg',
  }
});

<!-- Updating person with spread operator -->
const nextArtwork = { ...person.artwork, city: 'New Delhi' };
const nextPerson = { ...person, artwork: nextArtwork };
setPerson(nextPerson);

<!-- Calling setPosition -->
onPointerMove={e => {
  setPosition({
    x: e.clientX,
    y: e.clientY
  });
}}

```

## Conditional html and css

```
{condition ? (true) : (false)}

{condition && (true)}

<!-- Example -->

 {condition ? (
        <div>
          html/css when Condition is true
        </div>
      ) : (        
        <div>
        html/css when Condition is false
        </div>
      )}

 {condition && (
         <div>
          html/css when Condition is true
        </div>
      )}
      

```




## Passing props as object

```

<Avatar
  size={100}
  person={{ 
    name: 'Katsuko Saruhashi', 
    imageId: 'YfeOqp2'
  }}
/>

function Avatar({person , size }) {
  return (
    <img
      className="avatar"
      src={getImageUrl(person)}
      alt={person.name}
      width={size}
      height={size}
    />
  );
}



```


## Passing props as functions

```
export default function App() {
  return (
    <Toolbar
      onPlayMovie={() => alert('Playing!')}
      onUploadImage={() => alert('Uploading!')}
    />
  );
}

function Toolbar({ onPlayMovie, onUploadImage }) {
  return (
    <div>
      <Button onClick={onPlayMovie}>
        Play Movie
      </Button>
      <Button onClick={onUploadImage}>
        Upload Image
      </Button>
    </div>
  );
}

function Button({ onClick, children }) {
  return (
    <button onClick={onClick}>
      {children}
    </button>
  );
}

```


## spread syntax

```



function Profile({ person, size, isSepia, thickBorder }) {
  return (
    <div className="card">
      <Avatar
        person={person}
        size={size}
        isSepia={isSepia}
        thickBorder={thickBorder}
      />
    </div>
  );
}

Better syntax

function Profile(props) {
  return (
    <div className="card">
      <Avatar {...props} />
    </div>
  );
}




```

## Children prop (nested component)

The children prop is telling that the card component will have an other component inside it

```
import Avatar from './Avatar.js';

function Card({ children }) {
  return (
    <div className="card">
      {children}
    </div>
  );
}

export default function Profile() {
  return (
    <Card>
      <Avatar
        size={100}
        person={{ 
          name: 'Katsuko Saruhashi',
          imageId: 'YfeOqp2'
        }}
      />
    </Card>
  );
}

```

