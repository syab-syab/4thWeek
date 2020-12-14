<template>
<div class="container-fluid">
  <!--  -->
  <div class="row">
    <Header />
    <!-- <div class="bg-dark text-white text-center col-12 col-sm-12">
      <p class="h1">
        慰めチャット
      </p>
    </div> -->
    <div id="edit-zone" class="col-md-4 col-sm-12">
      <div class="input-group my-3">
        <input type="text" class="form-control" placeholder="何かつぶやいて" v-model="preChat">
        <div class="input-group-append">
          <button type="button" class="btn btn-outline-secondary" v-on:click="postChat">つぶやく</button>
        </div>
      </div>
    </div>
    <div id="display-zone" class="col-md-8 col-sm-12 p-0 bg-primary vh-100">
      <div id="chat-zone" class="p-5">
        <ul class="p-0">
          <!-- 奇数がユーザー, 偶数がbot -->
            <li class="p-3" v-for="content in chats" v-bind:key="content.id">{{ content }}</li>
        </ul>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
data() {
    return {
      preChat: "",
      chats: []
    }
  },
  methods: {
    postChat: function() {
      this.chats.push(this.preChat)
      this.chats.push("君は悪くない")
      this.preChat = ""
    }
  }
}
</script>

<style>
#chat-zone {
  width: 100%;
}

#chat-zone > ul > li {
  list-style: none;
  height: auto;
  font-size: 2rem;
}

#chat-zone > ul > li:nth-child(odd) {
  background-color: greenyellow;
}

#chat-zone > ul > li:nth-child(even) {
  text-align: right;
  background-color: azure;
}

.v-enter-active {
  transition: opacity 1.6s;
  }

.v-enter {
  opacity: 0;
}
.v-enter-to {
  opacity: 1;
}

/* .container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
} */
</style>
