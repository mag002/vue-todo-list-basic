<template>
  <div id="container-box">
    <div class="box">
      <div class="left">
        <Info></Info>
      </div>
      <div class="right">
        <Nav></Nav>
        <div class="page-container">
          <router-view></router-view>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
// UI Inspire https://github.com/AlexanderGureev/simple-todo-app
import Info from "./components/Info.vue";
import Nav from "./components/Nav.vue";
// import { useRoute } from "vue-router";
import { useRouter } from "vue-router";

import { onMounted } from "vue";
export default {
  name: "App",
  components: {
    Info,
    Nav,
  },
  setup() {
    const router = useRouter();
    onMounted(() => {
      router.push({
        name: "Login",
      });
    });
  },
};
</script>
<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
}
$padding_5: 20px;
img {
  max-width: 100%;
}
.d-flex {
  display: flex;
}
.text-center {
  text-align: center;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
%perfect-center {
  display: flex;
  justify-content: center;
  align-items: center;
}
%border-bottom {
  border-bottom: 1px solid #d2d2d2;
}
%border-top {
  border-top: 1px solid #d2d2d2;
}

#container-box {
  @extend %perfect-center;
  height: 100vh;
  background: lightblue;
  .box {
    background: white;
    border-radius: 10px;
    min-height: 80vh;
    width: 80vw;
    box-shadow: 0 0 25px rgba(0, 0, 0, 0.16);
    display: flex;
    .left {
      width: 30%;
      border-right: 1px solid #d2d2d2;
      #user-info {
        .basic-info {
          text-align: center;
          padding: $padding_5 * 2;
          img {
            border-radius: 10px;
            max-width: 150px;
            width: 100%;
          }
        }
        .task-summary {
          @extend %perfect-center;
          padding: 0 $padding_5 * 2 $padding_5 * 2;

          &-detail {
            width: 100%;
          }
        }
        .categories {
          padding: $padding_5 * 2;
          @extend %border-top;
          h3 {
            margin-bottom: $padding_5;
          }
          .category-list {
            display: flex;
            width: 100%;
            overflow: auto;
            flex-wrap: wrap;
            justify-content: space-between;
            .category {
              @extend %perfect-center;
              margin-right: $padding_5;
              margin-bottom: $padding_5;
              .color {
                display: block;
                width: 25px;
                height: 10px;
                background: tomato;
                margin-right: 10px;
              }
            }
          }
        }
      }
    }
    .right {
      width: 70%;
      nav {
        ul {
          display: flex;
          width: 100%;
          list-style-type: none;
          padding: 0px;
          @extend %border-bottom;
          li,
          a {
            cursor: pointer;
            color: black;
            text-transform: uppercase;
            padding: $padding_5 * 1.5 $padding_5;
            text-decoration: none;
          }
        }
      }
      .page-container {
        #todo-list {
          .todo-actions {
            display: flex;
            justify-content: space-between;
            padding: $padding_5;
            button {
              border-radius: 10px;
              padding: 10px 20px;
              border: none;
              font-weight: bold;
              color: white;
              cursor: pointer;
              background: lightskyblue;
              &:hover {
                background: darken(lightskyblue, 50%);
              }
            }
            .task-status-filter {
              padding: 10px;
              display: flex;
              justify-content: flex-end;
              & > div {
                margin: 0px 10px;
                padding: 5px 10px;
                cursor: pointer;
                &.active {
                  border-radius: 1000px;
                  background: lightskyblue;
                  color: white;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
