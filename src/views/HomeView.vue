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
          </div>
        </div>
      </div>
    </div>
    <div class="hero-foot">
      <div class="container">
        <img src="@/assets/dev_art.png" class="dig-art" />
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
          <button class="button is-rounded">
            <RouterLink to="/resume">My Resume</RouterLink>
          </button>
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
            languages to build some cool stuff. Here are a few of my favorites:
          </h2>
          <button class="button is-rounded">
            <RouterLink to="/projects">My Projects</RouterLink>
          </button>
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
</template>

<script setup lang="ts">
import SkillColumn from './SkillColumn.vue';
import TestimonialView from './TestimonialView.vue';
import { ref, type Ref } from 'vue';

interface SkillColumnTemplate {
  title: string;
  description: string;
  subtitle1: string;
  subtitle1Description: string;
  subtitle2: string;
  subtitle2ListItems: string[];
}

const skillColumnData: Ref<SkillColumnTemplate[]> = ref([
  {
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
    title: 'Project Manager',
    description: 'I have managed multiple teams of developers and designers on various projects.',
    subtitle1: 'Skills',
    subtitle1Description: 'Technical Communication, Team Leadership, Problem Solving',
    subtitle2: 'Management Tools',
    subtitle2ListItems: ['Agile/Scrum', 'Kanban', 'GitHub', 'Jira', 'Trello', 'Slack', 'MS Office'],
  },
  {
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
    imagePath: '/src/assets/brett-profile.jpeg',
    quote: `"Working with Harrison has been a pleasure. He became comfortable with our codebase incredibly
      quickly and has built multiple key features of the website. His code is clean, readable, and
      scalable. [He] does such a good job communicating the work he is doing and making sure that
      all requirements are being fulfilled. All around, Harrison has been a wonderful addition to
      our team."`,
    name: 'Brett Fischer',
    title: 'Frontend Engineer',
  },
  {
    imagePath: '/src/assets/justis-profile.jpeg',
    quote: `"Harrison is one of the best developers I have ever worked with. He has a deep knowledge 
      of our tech stack and does a really good job keeping up with new technologies. He keeps our whole
      site running single-handedly. He is prompt in responding, clear in requests, and a great team leader.
      I would highly recommend Harrison for any position for which he is being considered. "`,
    name: 'Justis Brown',
    title: 'Full Stack Developer',
  },
]);
//<a href="https://www.freepik.com/free-vector/storage-designs-set_957450.htm#query=digital%20art%20web%20server%20development&position=35&from_view=search&track=ais">Image by newelement</a> on Freepik
</script>
