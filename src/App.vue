<template>
  <transition name="fade" tag="div" class="wrapper" mode="out-in">
    <div class="wrapper" v-if="isLoaded" id="app">
      <LandingPage :user="user" />
      <Description
        :user="user"
        :content="findSlug('description')"
        :links="findSlug('links')"
      />
      <Experience :content="findSlug('experiences')" />
      <Skills :content="findSlug('skills')" />
      <Projects :content="findSlug('projects')" />
      <Footer :user="user" :links="findSlug('links')" />
    </div>
  </transition>
</template>

<script>
import LandingPage from "./components/LandingPage.vue";
import Description from "./components/Description.vue";
import Experience from "./components/Experience.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    LandingPage,
    Description,
    Experience,
    Skills,
    Projects,
    Footer,
  },
  data: () => ({
    isLoaded: false,
    user: {},
    posts: [],
  }),
  methods: {
    findSlug(slug) {
      return this.posts.find((item) => {
        return item.slug === slug;
      });
    },
  },
  created() {
    this.posts = [
      {
        slug: "projects",
        title: "projects",
        metadata: {
          items: [
            {
              title: "CRUD de Personas",
              content:
                "Es una plataforma para eliminar, agregar, listar y actualizar una persona con uso de Blockchain Ethereum. Desarrollada en HTML - Bootstrap, NodeJs de Backend y de almacenamiento una Red BlockChain Ethereum",
              image: "crud_blockchain.gif",
              tag: "Blockchain Ethereum",
              color: "blue",
              date: "2021-07-01",
            },
            {
              title: "Cultivos - Sena",
              content:
                "Desarrollo de una herramienta tecnológica para la planeación de cultivos de interés comercial en el departamento del Atlántico, mediante la utilización de técnicas de minería de datos e inteligencia artificial. <br/><br/> Link: <a href='https://github.com/jdcastro6464/cultivos' target='_blank'>https://github.com/jdcastro6464/cultivos</a>",
              image: "cultivos.png",
              tag: "Machine Learning",
              color: "purple",
              date: "2021-03-01",
            },
            {
              title: "Tiger BigData - Sena",
              content:
                "Uso de Tecnologías Inteligentes para la Gestión Eficiente de los recursos Hídricos mediante Big Data en Malambo (Atlántico) 2020",
              image: "tiger.png",
              tag: "Neurona Artificial - Keras",
              color: "green",
              date: "2021-08-01",
            },
            {
              title: "Airline Blockchain Ethereum",
              content:
                "Plataforma desarrollada en aprendizaje para la compra de voletos de vuelos, desarrollada en ReactJS y Blockchain Ethereum",
              image: "airline_blockchain.png",
              tag: "Blockchain Ethereum - ReactJs",
              color: "blue",
              date: "2021-07-20",
            },
            {
              title: "Encuesta de Caracterización",
              content:
                "Plataforma desarrollada para la gestión de aprendices en el area de Bienestar al aprendiz del Centro Nacional Colombo Alemán, y brindarle seguimiento al inicio de la formación.<br/><br/>Link: <a href='https://colomboalemanbq.com/encuesta_caracterizacion/' target='_blank'>https://colomboalemanbq.com/encuesta_caracterizacion/</a>",
              image: "encuesta_caracterizacion.png",
              tag: "PHP",
              color: "white",
              date: "2018-06-01",
            },
            {
              title: "Gestión Educativa - CNCA",
              content:
                "Plataforma desarrollada la publicación de programas complementarios del Centro Nacional Colombo Alemán, a la vez poder administrar los cursos, inscripciones y áreas especialidad de cada curso.<br/><br/>Link: <a href='https://colomboalemanbq.com/gestioneducativa/' target='_blank'>https://colomboalemanbq.com/gestioneducativa/</a>",
              image: "gestionedu.png",
              tag: "Software",
              color: "turquoise",
              date: "2018-12-15",
            },
            {
              title: "Horarios Colombo Alemán",
              content:
                "Herramienta web para la administración de horarios de formación titulada en el Sena Centro Nacional Colombo Alemán, y brindar seguimiento a los horarios publicados<br/><br/>Link: <a href='https://colomboalemanbq.com/horariocnca/' target='_blank'>https://colomboalemanbq.com/horariocnca/</a>",
              image: "horarios.png",
              tag: "Software",
              color: "purple",
              date: "2019-06-01",
            },
            {
              title: "Sisnova",
              content:
                "Sistema de gestión documental de Sennova Centro Nacional Colombo Alemán.<br/><br/>Link: <a href='https://colomboalemanbq.com/sisnova/' target='_blank'>https://colomboalemanbq.com/sisnova/</a>",
              image: "sisnova.png",
              tag: "Aplicativo Web",
              color: "green",
              date: "2019-06-15",
            },
            {
              title: "Vilib",
              content:
                "Este desarrollo aplica para el proceso de solicitud de un crédito bajo modalidad de Libranza enfocado en la seguridad mediante la trazabilidad, iniciando desde el momento en que el Cliente solicita un crédito, seguido con base a los datos ingresados por el Cliente de Listas las diferentes opciones ofrecidas por las Entidades Financieras y finalizando cuando el Cliente selecciona una opción.<br/><br/>Link: <a href='https://vilib.co' target='_blank'>https://vilib.co</a>",
              image: "vilib.png",
              tag: "Plataforma Web",
              color: "orange",
              date: "2020-02-15",
            },
            {
              title: "Fitsurgery",
              content:
                "Cirugía Plástica & Turismo Médico Estético en Colombia 🚀 ¡Cientos de Casos Exitosos! Lipoescultura, Mamoplastia, BBL, Abdominoplastia, Lipovaser, Perfilamiento Facial.<br/><br/>Link: <a href='https://fitsurgery.com' target='_blank'>https://fitsurgery.com</a>",
              image: "fitsurgery.png",
              tag: "Software Web",
              color: "blue",
              date: "2020-06-15",
            },
            {
              title: "Corfal CRM",
              content:
                "CRM para el seguimiento de un crédito por libranza.<br/><br/>Link: <a href='https://vilib.co/corfal/pyh/' target='_blank'>https://vilib.co/corfal/pyh/</a>",
              image: "corfal.png",
              tag: "CRM",
              color: "white",
              date: "2021-03-15",
            },
            {
              title: "Escrutinio Blockchain Ethereum",
              content:
                "Herramienta para el almacenamiento de información de Escrutinio, utilizando como almacenamiento una red privada blockchain Ethereum.",
              image: "escrutinio.png",
              tag: "Blockchain Ethereum",
              color: "green",
              date: "2021-01-01",
            },
          ],
          title: "Mis Proyectos",
          description: "Esta es mi historia",
        },
      },
      {
        slug: "skills",
        title: "skills",
        metadata: {
          items: [
            {
              title: "Red Ethereum",
              img: "ethereum.png",
            },
            {
              title: "Solidity Smart Contracts",
              img: "solidity.png",
            },
            {
              title: "HTML",
              img: "html.png",
            },
            {
              title: "CSS",
              img: "css.png",
            },
            {
              title: "Javascript",
              img: "javascript.jpg",
            },
            {
              title: "JQuery",
              img: "jQuery-logo.png",
            },
            {
              title: "PHP",
              img: "php.png",
            },
            {
              title: "Java Web",
              img: "javaweb.png",
            },
            {
              title: "VueJS",
              img: "vuejs.png",
            },
            {
              title: "ReactJS",
              img: "reactjs.png",
            },
            {
              title: "NodeJS",
              img: "nodejs.png",
            },
            {
              title: "Python",
              img: "python.png",
            },
            {
              title: "Git/Github",
              img: "Octocat.png",
            },
            {
              title: "Mysql",
              img: "mysql-logo.png",
            },
            {
              title: "BD2",
              img: "db2.png",
            },
          ],
          title: "HABILIDADES",
          description: "Mis conocimientos",
        },
      },
      {
        slug: "links",
        title: "links",
        metadata: {
          facebook: "https://www.facebook.com/Juandavid.CastroxD",
          instagram: "https://www.instagram.com/juanda.0320/",
          linkedin:
            "https://www.linkedin.com/in/juan-david-castro-hoyos-6a0254219/",
          github: "https://github.com/jdcastro464",
        },
      },
      {
        slug: "description",
        title: "description",
        metadata: {
          pres_second:
            "Siempre me ha gustado trabajar en proyectos utilizando las habilidades que no tengo o que incluso me sobraban, programación pura en lenguajes como PHP, Java, Vuejs, ReactJs, NodeJs, Solidity, Blockchain Ethereum, Python. Me apasiona el back-end en cualquier lenguaje de programación. Esto me ha permitido a ser autónomo y aprender por mi cuenta, ciertamente con y sin dificultades. ¡Pero siempre logré superar los obstáculos y resolver los problemas que encontré!",
          pres_first:
            "Soy desarrollador Full-Stack. Tengo un título como tecnólogo en análisis y desarrollo de software, también tengo un certificado en desarrollo de Solidity lenguaje de Blockchain Ethereum. Siempre me ha apasionado el desarrollo de software e indagar en nuevas tendencias de programación, me considero una persona con alto grado de aprendizaje. Me gusta al igual trabajar en equipo y obtener buenos resultados.",
          pres_title: "¿ Quién soy ?",
          description: "Espero conocerte",
          title: "Acerca de mi",
        },
      },
      {
        slug: "experiences",
        title: "experiences",
        metadata: {
          description: "Profesional y académica",
          title: "Experiencia",
          professional: [
            {
              year: "10.2021 - Actualidad",
              title: "Thomas Processing & Systems",
              content:
                "Desarrollador de Software: Desarrollo de aplicaciones web a la medida TPS",
            },
            {
              year: "11.2018 - 12.2021",
              title: "SENA - Centro Nacional Colombo Alemán",
              content:
                "Desarrollador de Software: Desarrollo de aplicaciones web a la medida del Centro Nacional Colombo Alemán",
            },
            {
              year: "12.2018",
              title: "Thomas Processing & Systems",
              content:
                "Desarrollo de herramienta de Escrutinio utilizando una red ethereum blockchain",
            },
            {
              year: "01.2021",
              title: "Freelancer",
              content:
                "Desarrollo de herramienta CRM para la administración de créditos de libranzas",
            },
            {
              year: "01.2020",
              title: "Freelancer",
              content:
                "Desarrollo de herramienta para créditos de libranzas al sector educativo",
            },
          ],
          academic: [
            {
              year: "2022",
              title: "Máster en Vue JS de cero a experto",
              content: "Udemy.com",
            },
            {
              year: "2021",
              title:
                "Curso de Fundamentos de Redes Neuronales con Python y Keras",
              content: "Platzi.com",
            },
            {
              year: "2021",
              title: "Conviértete en desarrollador Blockchain con Ethereum",
              content: "Udemy.com",
            },
            {
              year: "2021",
              title: "Curso de React.js 2019",
              content: "Platzi.com",
            },
            {
              year: "2021",
              title: "Curso Básico de Vue.js 2",
              content: "Platzi.com",
            },
            {
              year: "2021",
              title: "Curso de Node.js",
              content: "Platzi.com",
            },
            {
              year: "2020",
              title: "Aprende a programar con Python (Edición 2020)",
              content: "Mastermind.com",
            },
            {
              year: "2016 - 2018",
              title:
                "Tecnólogo en análisis y desarrollo de sistemas de información",
              content: "Sena - Centro Nacional Colombo Alemán",
            },
          ],
        },
      },
    ];

    this.user = {
      name: "Juan David Castro Hoyos",
      status:
        "Desarrollador Full-Stack Javascript, Php, Java, Solidity (BlockChain Ethereum)",
      email: "jdcastro464@gmail.com",
      phone: "+57 3023393413",
      city: "Barranquilla, Atlántico",
      lang: "Español",
      photo: "photo.jpg",
    };

    this.isLoaded = true;
  },
};
</script>

<style scoped lang="scss">
@import "@/styles/constants.scss";

#app {
  font-family: Montserrat-Regular, serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.wrapper {
  height: 100%;
}
</style>
