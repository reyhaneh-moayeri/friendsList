<template>
  <header>
    <h2>Friends List</h2>
  </header>
  <friend-contact
    v-for="friend in friends"
    :key="friend.id"
    :id="friend.id"
    :name="friend.name"
    :email-address="friend.email"
    :phone-number="friend.phone"
    :is-favourit="friend.isFavourit"
    @toggle-favourite="toggleFavouritStatus"
  ></friend-contact>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: "reyhaneh",
          name: "reyhaneh moayerirad",
          email: "reyhanehrm333@gmail.com",
          phone: 987654,
          isFavourit: false,
        },
        {
          id: "sara",
          name: "sara ahmadi",
          email: "sara@localhost.com",
          phone: 456789,
          isFavourit: true,
        },
        {
          id: "Ali",
          name: "Ali Mahmoodi",
          email: "ali@localhost.com",
          phone: 234567,
        },
      ],
    };
  },

  methods: {
    toggleFavouritStatus(friendId) {
      const identifiedFriend = this.friends.find(
        (friend) => friend.id === friendId
      );
      identifiedFriend.isFavourit = !identifiedFriend.isFavourit;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: "Jost", sans-serif;
}

body {
  margin: 0;
}

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #d46bfa;
  color: #833471;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

#app li {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
  list-style-type: none;
}

#app h2 {
  font-size: 2rem;
  color: #fff;
  margin: 0 0 1rem 0;
}

#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid#833471;
  background-color: #833471;
  color: white;
  padding: 0.5rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
  margin: 0.5rem;
  transition: 0.5s cubic-bezier(0.165, 0.84, 0.44, 1);
  font-weight: bold;
}
#app button:hover {
  background: #fff;
  color: #6f1e51;
}
</style>
