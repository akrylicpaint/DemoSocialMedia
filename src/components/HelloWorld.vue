<template>
  <div>
    <div style="display: flex">
      <img class="header" alt="favicon" src="../assets/profile.png" />
      <p>akrylic_paint</p>
    </div>
    <img alt="Vue logo" class="image" src="../assets/post.jpg" />
    <br />
    <el-row>
      <el-button type="primary" v-if="liked" @click="unlikeit"
        >Liked {{ likes }}</el-button
      >
      <el-button v-else @click="likeit">Like {{ likes }}</el-button>
      <el-button @click="comment">Comment</el-button>
      <el-button>Share</el-button>
    </el-row>
  </div>
</template>

<script>
import { ElButton } from "element-plus";
export default {
  name: "HelloWorld",
  components: { ElButton },
  props: {
    msg: String,
  },
  data() {
    return {
      liked: false,
      comment: null,
      likes: 0,
    };
  },
  methods: {
    likeit() {
      this.liked = true;
      this.likes = this.likes + 1;
    },
    unlikeit() {
      this.liked = false;
      this.likes = this.likes - 1;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.image {
  height: 450px;
  width: 800px;
  padding-right: 10%;
  margin-left: 10%;
}
p {
  padding-left: 10px;
  font-weight: bold;
}
.header {
  margin-left: 20%;
  height: 25px;
  width: 25px;
  padding-top: 10px;
  border-radius: 10%;
}
</style>
