<template>
  <div class='container'>
    <div class='cbCon'><input id='cb' class='complete' type='checkbox'/>
      <div></div>
    </div>
    <span @click='checkOnText'>{{ todoName || 'Have a Meal' }}</span>
    <button><img src='~/assets/img/trash.svg' width='20' alt='trashcan'/>
    </button>
  </div>
</template>
<script>

export default {
  name: 'ToDoItem',
  props: [
      'todoName'
  ],
  data() {
    return {
    };

  },
  methods: {
    checkOnText(event) {
      // Gets the Checkbox of same Task
      let sibling = (event.target.previousSibling).firstChild;
      sibling.checked = !sibling.checked
    }
  }
};
</script>

<style scoped>
.container {
  margin: 20px auto;
  display: flex;
  align-items: center;
  gap: 20px;
  background: #262828;
  width: fit-content;
  padding: 5px 15px 5px 10px;
  border-radius: 20px;
}

.cbCon {
  border-radius: 3px;
  position: relative;
  width: 24px;
  height: 24px;
  margin: 5px;
  float: left;
  border: 2px solid #fff;
  box-sizing: border-box;
}

.cbCon div {
  border-radius: 1px;
  margin-top: 3px;
  margin-left: 3px;
  width: 70%;
  height: 70%;
  display: flex;
  justify-content: center;
  align-items: center;
  line-height: 25px;
  transition: .3s ease;
}

.complete {
  position: absolute;
  top: 0;
  left: 0;
  width: 24px;
  height: 24px;
  opacity: 0;
  cursor: pointer;
}

.complete:checked ~ div {
  background-color: #00ab35;

}

span {
  font-size: 24px;
  line-height: 40px;
  padding-bottom: 3px;
  min-width: 400px;
}

button {
  background: #313335;
  border-radius: 100%;
  padding: 6px;
}

button:active {
  background-color: #474c4c;
}

button:hover {
  animation: shake 0.4s;
  animation-iteration-count: infinite;
}

@keyframes shake {
  0% {
    transform: rotate(0deg);
  }
  20% {
    transform: rotate(-6deg);
  }
  40% {
    transform: rotate(6deg);
  }
  60% {
    transform: rotate(-6deg);
  }
  80% {
    transform: rotate(6deg);
  }
  100% {
    transform: rotate(-6deg);
  }
}
</style>