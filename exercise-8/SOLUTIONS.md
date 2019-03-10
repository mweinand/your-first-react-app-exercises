# Possible Solutions

## FriendDetail Route

```jsx
import { BrowserRouter, Route } from 'react-router-dom';
import FriendDetail from './friend-detail/FriendDetail.entry';
...

function App() {
  return (
    <BrowserRouter>
      <div className={styles.app}>
        <header className={styles.appHeader}>
          <h1 className={styles.appTitle}>Exercise 11</h1>
          <h2 className={styles.subTitle}>React Router</h2>
        </header>
        <div className={styles.exercise}>
          <Route path="/" exact component={Friends} />
          <Route path="/friends/:id" component={FriendDetail} />
        </div>
      </div>
    </BrowserRouter>
  );
}

```

## FriendProfile Link

```jsx
import { Link } from 'react-router-dom';
...

export default function FriendProfile({ id, name, image }) {
  return (
    <Link to={'friends/' + id}>
      <Card>
        <div className={styles.friendProfile}>
          <img src={image} alt={name} />
          <h3>{name}</h3>
        </div>
      </Card>
    </Link>
  );
}
```

## Active friend ID

```jsx
export default function({ match }) {
  // the match prop is passed in via react.router
  const friendId = match.params.id;
  const friend = friends.find(x => x.id === parseInt(friendId, 10));

  return <FriendDetail friend={friend} />;
}
```

## Home Link

```jsx
export default function({ friend }) {
  return (
    <Page>
      <div className={styles.friendDetail}>
        <div className={styles.toolbar}>
          <Link to="/">&lt; Home</Link>
        </div>
        <Card>
          <div className={styles.cardContents}>
            <h1>{friend.name}</h1>
            <FriendFlipper friend={friend} />
            <p>{friend.bio}</p>
          </div>
        </Card>
      </div>
    </Page>
  );
}
```
