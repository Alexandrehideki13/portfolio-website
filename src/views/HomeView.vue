<template>
  <section class="homeView">
    <header class="homeView__header">
      <div class="homeView__header-content">
        <h2 class="homeView__header-content-logo">&lt;HIDEV/></h2>
        <nav>
          <ul class="homeView__header-content-navigation">
            <li><a href="#about">Quem sou</a></li>
            <li><a href="#projects">Projetos</a></li>
            <li><a href="#services">Serviços</a></li>
            <li><a href="#skills">Conhecimentos</a></li>
            <li><a href="#contact">Contato</a></li>
          </ul>
        </nav>
      </div>
    </header>
    <main class="homeView__presentation">
      <div class="homeView__presentation-text">
        <h2 class="homeView__presentation-text-main">
          <span class="homeView__presentation-text-main-1">Oioi, eu sou</span>
          <br />
          <span class="homeView__presentation-text-main-2">
            Alexandre Hideki.
          </span>
        </h2>
        <p class="homeView__presentation-text-description">
          Desenvolvedor Front-end.
        </p>
      </div>
      <img
        src="@/assets/img/octocat.png"
        alt="Foto de Alexandre Hideki de perfil"
        class="homeView__presentation-photo"
      />
    </main>
    <section class="homeView__about" id="about">
      <div class="homeView__about-content">
        <img
          src="@/assets/img/icon-person.webp"
          alt="Memoji de Alexandre Hideki fazendo sinal de legal"
          class="homeView__about-content-photo"
        />
        <div class="homeView__about-content-about">
          <h2 class="homeView__about-content-about-title">&#10547; Quem sou</h2>
          <p class="homeView__about-content-about-text">
            Oioi, me chamo Alexandre Hideki, sou desenvolvedor front-end desde
            2021, desenvolvo interfaces web com código de qualidade e boas
            práticas de programação.
          </p>
        </div>
      </div>
    </section>
    <section class="homeView__projects" id="projects">
      <h2 class="homeView__projects-title">&#10547; Projetos &#11071;</h2>
      <h3 class="homeView__projects-text">Meus últimos projetos</h3>
      <div class="homeView__projects-content">
        <div
          v-for="project in projectsFiltered"
          :key="project.id"
          class="homeView__projects-content-project"
        >
          <CardProject :project="project" />
        </div>
      </div>
      <a
        class="homeView__projects-linkMoreProjects"
        href="https://github.com/Alexandrehideki13?tab=repositories"
        target="_blank"
      >
        <button class="homeView__projects-buttonMoreProjects">
          Acessar mais projetos
        </button>
      </a>
    </section>
    <section class="homeView__footer" id="services"></section>
  </section>
</template>

<script>
import CardProject from "@/components/CardProject.vue";

export default {
  components: {
    CardProject,
  },

  data: () => {
    return {
      projects: [
        {
          id: "1",
          title: "Dogs Social Media",
          typeWebsite: "REDE SOCIAL",
          photo: "portfolio-dekiDogs.jpg",
          stack: ["ReactJS"],
          description: "O Dogs Social Media é uma rede social para cachorros.",
          urlWebsite: "https://dekidogs.netlify.app/",
          urlRepository:
            "https://github.com/Alexandrehideki13/Dogs-Social-Media",
        },
      ],
    };
  },

  computed: {
    projectsFiltered() {
      let projectsArray = [
        { isBuilding: true },
        { isBuilding: true },
        { isBuilding: true },
      ];

      return projectsArray.map((project, index) => {
        if (index <= 2 && this.projects[index]) {
          return this.projects[index];
        }
        return project;
      });
    },
  },
};
// {
//   id: "2",
//   title: "a",
//   typeWebsite: "REDE SOCIAL",
//   photo: "../assets/img/portfolio-dekiDogs.png",
//   stack: ["ReactJS"],
//   description:
//     "O Dogs Social Media é uma rede social para cachorros.O Dogs Social Media é uma rede social para cachorros.",
//   urlWebsite: "https://dekidogs.netlify.app/",
//   urlRepository:
//     "https://github.com/Alexandrehideki13/Dogs-Social-Media",
// },
// {
//   id: "3",
//   title: "a",
//   typeWebsite: "REDE SOCIAL",
//   photo: "../img/portfolio-dekiDogs.png",
//   stack: ["ReactJS"],
//   description: "",
//   urlWebsite: "https://dekidogs.netlify.app/",
//   urlRepository:
//     "https://github.com/Alexandrehideki13/Dogs-Social-Media",
// },
// {
//   id: "4",
//   title: "a",
//   typeWebsite: "REDE SOCIAL",
//   photo: "../img/portfolio-dekiDogs.png",
//   stack: ["ReactJS"],
//   description: "",
//   urlWebsite: "https://dekidogs.netlify.app/",
//   urlRepository:
//     "https://github.com/Alexandrehideki13/Dogs-Social-Media",
// },
</script>
