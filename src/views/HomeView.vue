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
            <h2 class="subtitle is-size-5-tablet mt-6">Want to chat?</h2>
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

  <section
    id="about"
    class="section is-medium has-text-centered has-background-primary is-extended"
  >
    <div class="container">
      <div class="columns is-centered">
        <div class="column is-three-fifths">
          <h1 class="title is-spaced is-size-3-desktop is-size-4-mobile has-text-white title-font">
            Experienced Full Stack Software Engineer
          </h1>
          <h2
            class="subtitle is-size-5-desktop has-text-weight-normal has-text-white description-box"
          >
            I'm an experienced full stack software engineer with a passion for building beautiful,
            functional, and scalable web applications. I currently work as a Senior Full Stack
            Engineer at Fidelity Investments. I've developed many projects in various positions
            including as a full-time employee, a freelance developer, a project manager, and even as
            a technical cofounder. I excel at understanding complex problems, building powerful
            solutions, and developing products that customers need.
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

  <section id="projects" class="section is-medium has-text-centered has-background-primary">
    <div class="container">
      <div class="columns is-centered">
        <div class="column is-three-fifths">
          <h1 class="title is-spaced is-size-3-desktop is-size-4-mobile has-text-white title-font">
            My Projects
          </h1>
          <h2
            class="subtitle is-size-5-desktop has-text-weight-normal has-text-white description-box"
          >
            During my time as a full stack software engineer, I've had the opportunity to work on
            many fun, challenging, and rewarding projects. I've used many different technologies and
            languages to build some cool stuff. Here are a few of my favorites.
          </h2>
        </div>
      </div>
      <div v-for="(chunk, idx) in chunkedProjects" :key="idx" class="columns mt-6 is-centered">
        <div class="column is-one-third" v-for="(project, innerIdx) in chunk" :key="innerIdx">
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

  <section id="experience" class="section is-medium has-text-centered">
    <div class="container">
      <div class="columns is-centered">
        <div class="column is-three-fifths">
          <h1
            class="title is-spaced is-size-3-desktop is-size-4-mobile has-text-primary title-font"
          >
            My Experience
          </h1>
          <h2
            class="subtitle is-size-5-desktop has-text-weight-normal has-text-primary description-box"
          >
            I've had the opportunity to work in a few different developer and developer-adjacent
            roles over the years. I'm confident that my experience gained in these roles has
            prepared me to be a valuable asset to any team.
          </h2>
        </div>
      </div>
      <div class="columns is-centered experience-columns">
        <div class="column is-three-fifths">
          <ExperienceView
            v-for="(experience, idx) in myExperience"
            :key="idx"
            :company="experience.company"
            :position="experience.position"
            :time="experience.time"
            :position-two="experience.positionTwo"
            :time-two="experience.timeTwo"
            :hasLine="idx !== myExperience.length - 1"
          />
        </div>
      </div>
    </div>
  </section>

  <section class="section has-text-centered has-background-primary resume-box">
    <div class="container">
      <h2 class="subtitle is-size-5-tablet mt-6 has-text-white">Looking for a full resume?</h2>
      <div class="level">
        <div class="level-item has-text-centered">
          <a
            class="button is-white is-outlined is-rounded is-medium"
            href="mailto:dev@harrisonbludworth.com"
            >Email Me</a
          >
        </div>
      </div>
    </div>
  </section>

  <section class="section has-text-centered testimonials is-medium has-background-white">
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
          <p class="mt-6">Made by me. © 2024.</p>
          <p class="mt-5 is-size-7">Built with Vue, Bulma, and TypeScript.</p>
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
import ExperienceView from '@/components/ExperienceView.vue';
import { ref, type Ref, computed } from 'vue';

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
    title: 'Full Stack Software Engineer',
    description:
      'I can build beautiful, functional, and scalable web applications from the ground up.',
    subtitle1: 'Dev Tools',
    subtitle1Description: 'Git, Docker, AWS, Linux, GitHub, VS Code, Postman',
    subtitle2: 'Languages and Frameworks',
    subtitle2ListItems: [
      'TypeScript',
      'Node.js',
      'GraphQL',
      'Vue',
      'Angular',
      'Express',
      'SQL',
      'HTML/CSS',
      'JavaScript',
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
      'Built and Launched SaaS Product',
      '#12 Product Hunt Launch',
      'Worked with 20+ B2B Customers',
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
      'The Old Assyrian Research Environment is a digital humanities project at BYU that helps historians analyze and perform research on ancient cuneiform tablets. It is built with Vue, Node.js, TypeScript, and SQL. During my time at BYU, I was the primary contributor to the project.',
    viewLink: 'https://oare.byu.edu',
    githubLink: 'https://github.com/oaregithub/oare_mono',
  },
  {
    title: 'MicDrop',
    imagePath: 'micdrop.png',
    description:
      'MicDrop was a Chrome extension that allowed users to send and receive audio messages from within Gmail. It allowed for basic customization and was built with Vue, Node.js, and TypeScript. I was the technical cofounder and primary developer before MicDrop was shut down.',
    githubLink: 'https://github.com/hbludworth/micdrop',
  },
  {
    title: 'Firebase Authentication Template',
    imagePath: 'firebase.png',
    description:
      'This is a template for a Firebase Authentication system. It is a MEVN app built using TypeScript. It is meant to be a starting point for any project that requires user authentication and features both frontend and backend route guarding.',
    githubLink: 'https://github.com/hbludworth/firebase-template',
  },
  {
    title: 'WebSocket Chat App',
    imagePath: 'chat.png',
    description:
      'This is a simple chat app that uses WebSockets to allow for real-time communication between users and uses my Firebase Authentication Template for user authentication. The WebSockets are built to reconnect automatically if the connection is lost.',
    githubLink: 'https://github.com/hbludworth/websocket-chat',
  },
  {
    title: 'My Portfolio',
    imagePath: 'portfolio.png',
    description:
      'This is the page that you are currently viewing. It is meant to highlight my abilities and demonstrate my excitement for software development. It is an extremely simple portfolio page built with Vue, Bulma, and TypeScript and is hosted on AWS S3.',
    githubLink: 'https://github.com/hbludworth/portfolio',
  },
]);

const chunkedProjects = computed(() => {
  const myProjectsCopy = myProjects.value;
  const chunkedArrays = [];
  const chunkSize = 3;
  while (myProjects.value.length > 0) {
    chunkedArrays.push(myProjectsCopy.splice(0, chunkSize));
  }
  return chunkedArrays;
});

interface ExperienceTemplate {
  company: string;
  position: string;
  time: string;
  positionTwo?: string;
  timeTwo?: string;
}

const myExperience: Ref<ExperienceTemplate[]> = ref([
  {
    company: 'Fidelity Investments',
    position: 'Senior Full Stack Software Engineer',
    time: 'December 2024 - Present',
    positionTwo: 'Full Stack Software Engineer',
    timeTwo: 'August 2023 - December 2024',
  },
  {
    company: 'Brigham Young University - Department of History',
    position: 'Full Stack Software Engineer - Team Lead - Project Manager',
    time: 'October 2020 - July 2023',
  },
  {
    company: 'MicDrop',
    position: 'Technical Cofounder',
    time: 'January 2022 - February 2023',
  },
  {
    company: 'Entrata',
    position: 'Search Engine Optimization Intern - Team Leader',
    time: 'January 2021 - April 2021',
  },
  {
    company: 'Vivint Smart Home',
    position: 'Account Specialist',
    time: 'June 2020 - October 2020',
  },
  {
    company: 'Filevine',
    position: 'Intake Specialist',
    time: 'September 2019 - March 2020',
  },
]);
</script>
