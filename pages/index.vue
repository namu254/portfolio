<template>
  <div>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2">
      <div class="p-6 text-black mt-12 md:mt-20 md:pl-20">
        <img
          id="menu"
          v-on:click="openStack"
          class="p-6 md:p-10 absolute top-0 right-0 z-10 cursor-pointer"
          src="~/assets/menu.svg"
        />

        <h1 class="name font-medium text-lg md:text-xl">About Me</h1>
        <h1 class="font-medium text-3xl md:text-6xl leading-snug">
          Hello, my name is Namu
        </h1>
        <p class="about text-lg md:text-2xl pt-4 md:pt-10">
          I'm a full-stack developer. Welcome to my personal website. I create
          products that make a difference. Innovation and problem solving is my
          passion. If interested contact me through;
          <a href="https://github.com/namu254">GitHub</a>,
          <a href="mailto:namuroot254@gmail.com">Email</a> or
          <a href="https://www.linkedin.com/in/namu254/">LinkedIn</a>
        </p>
        <button
          v-on:click="openProjects"
          class="btn text-white py-2 px-4 mr-6 rounded-full mt-10"
        >
          View Projects
        </button>
        <button
          v-on:click="openStack"
          class="btn text-white py-2 px-4 rounded-full mt-10"
        >
          View Stack
        </button>
      </div>

      <div class="relative h-auto md:h-screen lg:h-screen">
        <img
          class="logo object-scale-down w-full p-12 md:p-10"
          src="~/assets/avatar.png"
        />
      </div>
    </div>
    <div id="mySidenav" class="sidenav overflow-y-scroll">
      <div class="topper h-6"></div>
      <img
        v-on:click="closeStack"
        class="p-2 absolute top-6 closeStack left-0 z-10 cursor-pointer shadow-lg"
        src="~/assets/close.svg"
      />
      <h1 class="text-center pt-4 text-2xl text-black">My Stack</h1>
      <div
        class="stack divide-y divide-gray-400 text-white font-medium absolute bottom-0 right-0 left-0"
      >
        <div class="relative item border-t-2 border-grey-300">
          <p class="absolute right-0 top-0 m-4 text-base">
            Cross Platform App Development
          </p>
          <img
            class="inline object-contain h-10"
            src="~/assets/logos/flutter.png"
          />
        </div>
        <div class="item relative">
          <p class="absolute right-0 top-0 m-4 text-base">
            Frontend Development
          </p>
          <div>
            <img
              class="inline object-contain h-10 mr-4"
              src="~/assets/logos/vue.png"
            />
            <img
              class="inline object-contain h-10 mr-4"
              src="~/assets/logos/web.png"
            />
          </div>
        </div>
        <div class="item relative">
          <p class="absolute right-0 top-0 m-4 text-base">
            Backend Development
          </p>
          <img
            class="inline object-contain h-10"
            src="~/assets/logos/node.png"
          />

          <img
            class="inline object-contain h-10"
            src="~/assets/logos/django.png"
          />
        </div>
        <div class="item relative">
          <p class="absolute right-0 top-0 m-4 text-base">Foundation</p>
          <img
            class="inline object-contain h-10"
            src="~/assets/logos/python.svg"
          />
        </div>
      </div>
    </div>
    <div id="myBottomPage" class="bottomPage overflow-y-scroll">
      <div class="topper h-6"></div>
      <img
        v-on:click="closeProjects"
        class="p-2 md:p-2 closeProjects absolute top-6 left-0 z-10 cursor-pointer shadow-lg"
        src="~/assets/close.svg"
      />
      <h1 class="text-center text-3xl font-medium pt-4 md:pt-10 lg:pt-10">
        Projects
      </h1>
      <div class="projectsContainer flex flex-wrap justify-center">
        <div
          class="project shadow rounded m-6 p-4"
          v-for="project in projects"
          :key="project.img"
        >
          <img
            class="h-64 w-64 object-contain cursor-pointer"
            :src="project.img"
          />
          <div class="text-center mt-8">
            <span class="year p-2 text-white rounded">{{ project.year }}</span>
            <p class="p-4">{{ project.name }}</p>
            <a v-bind:href="project.link" class="p-4 text-blue-400">Visit</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          name: " eLearning Platform",
          link: "https://github.com/namu254/assignment-sys",
          year: "2018",
          img:
            "https://user-images.githubusercontent.com/29103362/65970367-149f5580-e46f-11e9-9717-bb46320dac23.png",
        },
        {
          name: "Matatu Booking App",
          link: "https://github.com/namu254/matatu-online-booking",
          year: "2019",
          img:
            "https://user-images.githubusercontent.com/29103362/65965391-3dbbe800-e467-11e9-8654-1a283a13168f.png",
        },
        {
          name: "Contactless Menu",
          link: "http://icn-digital-menu-guest.firebaseapp.com/",
          year: "2020",
          img:
            "https://user-images.githubusercontent.com/29103362/85670125-3e696e00-b6c9-11ea-98de-50ec985af9ad.jpg",
        },
      ],
    };
  },
  head() {
    return {
      title: "if(Interested) {Contact Me}",
    };
  },
  methods: {
    openStack: function () {
      if (window.innerWidth > 640) {
        document.getElementById("mySidenav").style.width = "50%";
      } else {
        document.getElementById("mySidenav").style.width = "100%";
      }
    },
    closeStack: function () {
      document.getElementById("mySidenav").style.width = "0";
    },
    openProjects: function () {
      document.getElementById("mySidenav").style.width = "0";
      document.getElementById("myBottomPage").style.height = "100%";
    },
    closeProjects: function () {
      document.getElementById("myBottomPage").style.height = "0%";
    },
  },
};
</script>

<style>
.btn {
  background-color: #00ab84;
}
.btn:hover {
  background-color: #009975;
}
.name {
  color: #00ab84;
}
.about a {
  color: #00ab84;
}

.item {
  text-align: center;
  display: inline-block;
  padding-top: 50px;
  padding-bottom: 50px;
  width: 100%;
  font-size: 1.5rem;
  transition: 0.5s;
  background-color: white;
  color: #000000;
}

@media (max-width: 640px) {
  .stack {
    border: none;
  }
}
/* .stack {
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%);
} */
@media (min-width: 640px) {
  .logo {
    height: 28rem;
    margin: 0;
    position: absolute;
    top: 50%;
    left: 50%;
    margin-right: -50%;
    transform: translate(-50%, -50%);
  }
}
.sidenav {
  height: 100%;
  width: 0;
  position: fixed;
  z-index: 10;
  top: 0;
  right: 0;
  background-color: #ffffff;
  overflow-x: hidden;
  transition: 0.5s;
  border-left: 1px solid #00ab84;
}

.topper {
  background-color: #00ab84;
}
.closeProjects {
  background-color: #00ab84;
}
.closeStack {
  background-color: #00ab84;
}
.bottomPage {
  position: fixed;
  width: 100%;
  height: 0;
  background-color: #ffffff;
  bottom: 0;
  z-index: 20;
  transition: 0.5s;
}
</style>
