<template>
  <section class="hero has-text-centered">
    <div class="hero-body">
      <div class="container">
        <div class="columns">
          <div class="column">
            <h1
              class="title is-spaced is-size-1-desktop is-size-2-tablet is-size-3-mobile title-font"
            >
              Hi, I'm Harrison
            </h1>
            <h2 class="subtitle is-size-4-tablet">I design and build quality software products.</h2>
            <img src="@/assets/profile.jpeg" class="mt-4 avatar" />
            <h2 class="subtitle is-size-5-tablet mt-6">Interested in my services?</h2>
            <div class="level">
              <div class="level-item has-text-centered">
                <a
                  class="button is-primary is-outlined is-rounded msg-btn is-medium"
                  href="mailto:dev@harrisonbludworth.com"
                  >Message Me</a
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section is-medium has-text-centered has-background-primary is-extended">
    <div class="container">
      <div class="columns is-centered">
        <div class="column is-three-fifths">
          <h1 class="title is-spaced is-size-3-desktop is-size-4-mobile has-text-white title-font">
            Full Stack Developer, Project Manager, and Technical Cofounder
          </h1>
          <h2
            class="subtitle is-size-5-desktop has-text-weight-normal has-text-white description-box"
          >
            I'm a full stack web developer with a passion for building beautiful, functional, and
            scalable web applications. I've developed many projects in various positions including
            as a full-time student, a freelance developer, a project manager, and even as a
            technical cofounder. I excel at understanding complex problems, building powerful
            solutions, and developing products that customers need. Having recently graduated in
            Entrepreneurship and Computer Science, I am currently looking for a full-time position
            as a software engineer and am confident that I can be a valuable asset to any team.
          </h2>
        </div>
      </div>
    </div>
  </section>

  <section class="section has-text-centered skillset">
    <div class="container">
      <div class="box">
        <div class="columns is-centered">
          <SkillColumn
            v-for="(skill, idx) in skillColumnData"
            :key="idx"
            :icon="skill.icon"
            :title="skill.title"
            :description="skill.description"
            :subtitle1="skill.subtitle1"
            :subtitle1-description="skill.subtitle1Description"
            :subtitle2="skill.subtitle2"
            :subtitle2-list-items="skill.subtitle2ListItems"
          />
        </div>
      </div>
    </div>
  </section>

  <section class="section is-medium has-text-centered has-background-primary">
    <div class="container">
      <div class="columns is-centered">
        <div class="column is-three-fifths">
          <h1 class="title is-spaced is-size-3-desktop is-size-4-mobile has-text-white title-font">
            My Projects
          </h1>
          <h2
            class="subtitle is-size-5-desktop has-text-weight-normal has-text-white description-box"
          >
            During my three years as a full stack developer, and as an Entrepreneurship and Computer
            Science student at Brigham Young University, I've had the opportunity to work on many
            fun, challenging, and rewarding projects. I've used many different technologies and
            languages to build some cool stuff. Here are a few of my favorites.
          </h2>
        </div>
      </div>
      <div class="columns is-centered mt-6">
        <div class="column is-one-third" v-for="(project, idx) in myProjects" :key="idx">
          <ProjectCard
            :title="project.title"
            :imagePath="project.imagePath"
            :description="project.description"
            :viewLink="project.viewLink"
            :githubLink="project.githubLink"
          />
        </div>
      </div>
    </div>
  </section>

  <section class="section has-text-centered testimonials is-medium">
    <div class="container">
      <h1 class="title is-spaced is-size-3-desktop is-size-4-mobile has-text-primary title-font">
        Testimonials
      </h1>
      <h2 class="subtitle is-size-5-desktop has-text-weight-normal has-text-primary mb-6">
        Some nice things my colleagues have said about me.
      </h2>
      <div class="box">
        <div class="columns is-centered">
          <TestimonialView
            v-for="(testimonial, idx) in testimonialData"
            :key="idx"
            :imagePath="testimonial.imagePath"
            :quote="testimonial.quote"
            :name="testimonial.name"
            :title="testimonial.title"
          />
        </div>
      </div>
    </div>
  </section>

  <footer class="footer has-background-primary has-text-white has-text-centered">
    <div class="container">
      <div class="columns">
        <div class="column">
          <img src="@/assets/logo-white.png" class="mt-4 logo-footer" />
          <p class="mt-6">
            <span class="icon mx-4">
              <a
                href="https://github.com/hbludworth"
                target="_blank"
                class="mdi mdi-github mdi-36px has-text-white"
              ></a>
            </span>
            <span class="icon mx-4">
              <a
                href="https://www.linkedin.com/in/hbludworth/"
                target="_blank"
                class="mdi mdi-linkedin mdi-36px has-text-white"
              ></a>
            </span>
            <span class="icon mx-4">
              <a
                href="mailto:dev@harrisonbludworth.com"
                target="_blank"
                class="mdi mdi-email-open mdi-36px has-text-white"
              ></a>
            </span>
          </p>
          <p class="mt-6">Made by me. © 2023.</p>
          <p class="mt-5 is-size-7">Built with Vue, Bulma, and TypeScript.</p>
          <p class="mt-1 is-size-7">Deployed on AWS S3.</p>
          <a
            href="https://github.com/hbludworth/portfolio"
            target="_blank"
            class="mt-1 is-size-7 has-text-white is-underlined"
            >Source</a
          >
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import SkillColumn from '@/components/SkillColumn.vue';
import TestimonialView from '@/components/TestimonialView.vue';
import ProjectCard from '@/components/ProjectCard.vue';
import { ref, type Ref } from 'vue';

interface SkillColumnTemplate {
  icon: string;
  title: string;
  description: string;
  subtitle1: string;
  subtitle1Description: string;
  subtitle2: string;
  subtitle2ListItems: string[];
}

const skillColumnData: Ref<SkillColumnTemplate[]> = ref([
  {
    icon: 'mdi-xml',
    title: 'Full Stack Developer',
    description:
      'I can build beautiful, functional, and scalable web applications from the ground up.',
    subtitle1: 'Dev Tools',
    subtitle1Description: 'Git, Docker, AWS, Linux, GitHub, VS Code, Postman',
    subtitle2: 'Languages and Frameworks',
    subtitle2ListItems: [
      'TypeScript',
      'Node.js',
      'Express',
      'Vue',
      'SQL',
      'React',
      'HTML/CSS',
      'JavaScript',
      'Python',
      'Java',
      'Swift',
      'C++',
    ],
  },
  {
    icon: 'mdi-account-multiple',
    title: 'Project Manager',
    description: 'I have managed multiple teams of developers and designers on various projects.',
    subtitle1: 'Skills',
    subtitle1Description: 'Technical Communication, Team Leadership, Problem Solving',
    subtitle2: 'Management Tools',
    subtitle2ListItems: ['Agile/Scrum', 'Kanban', 'GitHub', 'Jira', 'Trello', 'Slack', 'MS Office'],
  },
  {
    icon: 'mdi-cog',
    title: 'Technical Cofounder',
    description:
      'I have experience building and launching new software products as a startup cofounder.',
    subtitle1: 'Entrepreneurial Skills',
    subtitle1Description: 'Product Management, Business Strategy, Customer Development',
    subtitle2: 'Successes',
    subtitle2ListItems: [
      'Built and Launched 2 Products',
      'Led 4 Product Teams',
      '#12 Product Hunt Launch',
      'Worked with 40+ B2B Customers',
      'Pushed 400,000+ lines of code',
      '200+ MAU in 3 months',
    ],
  },
]);

interface TestimonialTemplate {
  imagePath: string;
  quote: string;
  name: string;
  title: string;
}

const testimonialData: Ref<TestimonialTemplate[]> = ref([
  {
    imagePath: 'brett-profile.jpeg',
    quote: `"Working with Harrison has been a pleasure. He became comfortable with our codebase incredibly
      quickly and has built multiple key features of the website. His code is clean, readable, and
      scalable. [He] does such a good job communicating the work he is doing and making sure that
      all requirements are being fulfilled. All around, Harrison has been a wonderful addition to
      our team."`,
    name: 'Brett Fischer',
    title: 'Frontend Engineer',
  },
  {
    imagePath: 'justis-profile.jpeg',
    quote: `"Harrison is one of the best developers I have ever worked with. He has a deep knowledge 
      of our tech stack and does a really good job keeping up with new technologies. He keeps our whole
      site running single-handedly. He is prompt in responding, clear in requests, and a great team leader.
      I would highly recommend Harrison for any position for which he is being considered."`,
    name: 'Justis Brown',
    title: 'Full Stack Developer',
  },
]);

interface ProjectTemplate {
  title: string;
  imagePath: string;
  description: string;
  viewLink?: string;
  githubLink?: string;
}

const myProjects: Ref<ProjectTemplate[]> = ref([
  {
    title: 'OARE',
    imagePath: 'oare.png',
    description:
      'The Old Assyrian Research Environment is a digital humanities project at BYU that helps historians analyze and perform research on ancient cuneiform tablets. It is built with Vue, Node.js, TypeScript, and SQL. I am the primary contributor to the project.',
    viewLink: 'https://oare.byu.edu',
    githubLink: 'https://github.com/oaregithub/oare_mono',
  },
  {
    title: 'MicDrop',
    imagePath: 'micdrop.png',
    description:
      'MicDrop is a Chrome extension that allows users to send and receive audio messages from within Gmail. It allows for basic customization and is built with Vue, Node.js, and TypeScript. (Note: Landing page is not my work. The full product itself is.)',
    viewLink: 'https://www.sendmicdrop.com',
    githubLink: 'https://github.com/hbludworth/micdrop',
  },
  {
    title: 'My Portfolio',
    imagePath: 'portfolio.png',
    description:
      'This is the page that you are currently viewing. It is meant to highlight my abilities and demonstrate my excitement for software development. It is an extremely simple portfolio page built with Vue, Bulma, and TypeScript and is hosted on AWS S3.',
    githubLink: 'https://github.com/hbludworth/portfolio',
  },
]);
</script>
