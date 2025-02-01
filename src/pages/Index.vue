<template>
  <Layout>
    <transition name="fade" appear>
      <main class="mt-1 mb-14">
        <div class="contain flex flex-col gap-7">
          <h1 class="font-semibold text-4xl">
            Hey <span class="wave" @click="startAnimation">👋</span>, I'm Subandhu
          </h1>
          <p class="text-dimGrey leading-8">
            I'm a Backend developer and Cloud enthusiast who thrives to craft solutions that are both simple and elegant. 
            I leverage a diverse array of technologies and tools (including AI) to solve the problem at hand.
            Besides coding, I am also a creative designer who loves to create impactful and functional designs.
            I'm a <span class="text-border">Jack of all trades</span> who is on the journey to set new benchmarks of excellence!
            <br>My email is:</br>
          </p>
          <Email :loopMessage="true" />
          <div class="flex items-center gap-5 text-dimGrey">
            <p>Also on:</p>

            <a href="https://www.linkedin.com/in/subandhu" target="_blank">
                <app-icon icon="fab fa-linkedin" size="lg"></app-icon>
            </a>

            <a href="https://github.com/retrojokerr" target="_blank">
              <app-icon icon="fab fa-github" size="lg"></app-icon>
            </a>

            <a href="https://twitter.com/sinhasubandhu" target="_blank">
              <app-icon icon="fab fa-twitter" size="lg"></app-icon>
            </a>


            <a href="mailto:subandhu2018@gmail.com">
              <app-icon icon="at" size="lg"></app-icon>
            </a>
          </div>
        </div>

      <!-- Projects List Section -->
      <div class="contain mt-16 flex flex-col gap-3">
        <a href="https://github.com/retrojokerr" target="_blank" class="font-semibold text-xl">
          Projects
          <app-icon class="text-dimGrey" icon="link" size="sm"></app-icon>
        </a>
        <div class="flex flex-col gap-3">
          <article class="flex md:flex-row flex-col md:items-center items-start md:gap-10 gap-0 md:pb-3 pb-5">
            <a href="https://github.com/retrojokerr/FILE-WIZARD" class="text-dimGrey decoration-cuppy underline underline-offset-4">
              File Wizard - A file conversion website using Python and AWS (Lambda, S3).
            </a>
          </article>
          
          <article class="flex md:flex-row flex-col md:items-center items-start md:gap-10 gap-0 md:pb-3 pb-5">
            <a href="https://www.shawty.site" class="text-dimGrey decoration-cuppy underline underline-offset-4">
              URL Shortener - A Node.js-based URL shortening service with MongoDB.
            </a>
          </article>

          <article class="flex md:flex-row flex-col md:items-center items-start md:gap-10 gap-0 md:pb-3 pb-5">
            <a href="https://github.com/retrojokerr/Social-Media-App-API" class="text-dimGrey decoration-cuppy underline underline-offset-4">
              Social Media App API - RESTful API with authentication, posts, comments, and real-time chat.
            </a>
          </article>
        </div>
      </div>

 <!-- Work Experience Section -->
 <div class="contain mt-16 flex flex-col gap-3">
          <h2 class="text-xl font-semibold">Work Highlights</h2>
          
          <div class="work-item">
            <h4 class="text-lg font-medium"><li>Software Developer Trainee at <a href="https://www.bsesdelhi.com/" target="_blank" class="text-blue-500">BSES Delhi</a></li></h4>
            <div class="text-dimGrey leading-8" style="margin-top: 20px ;">
              <p>I redesigned the PIMS UI, increasing user engagement by 30%, and built the frontend with JavaScript. I optimized the backend using Express.js and Node.js while managing the PostgreSQL database, ensuring 99.9% data integrity and 40% faster queries.</p>
              
            </div>
          </div>

          <div style="margin-top: 70px; align-self: flex-start; display: flex; align-items: flex-end;">
            <button style="background-color: #00B300;
                           border: none;
                           color: black;
                           padding: 10px 20px;
                           text-align: center;
                           text-decoration: none;
                           font-size: 16px;
                           cursor: pointer;">
              <a href="https://drive.google.com/file/d/1FYgIeMVlgDFZGA6Eu83SPlh66gTaxPju/view?usp=sharing" style="color: black; text-decoration: none;">Download Resume</a>
            </button>   
          </div>
        </div>

        <!-- Technologies List Section -->
        <div class="contain mt-5">
          <div class="mb-5">
            <h2 class="text-xl font-semibold">Let's Connect!</h2>
            <p class="mt-5">Feel free to reach out. Shoot me an <a href="mailto:hi@subandhu.tech" class="decoration-cuppy underline underline-offset-4">email</a>.</p>
          </div>
        </div>
      </main>
    </transition>
  </Layout>
</template>

<script>
import Email from '../components/Email.vue'
export default {
  metaInfo() {
    return {
      title: "Home | Subandhu.tech"
    }
  },
  components: {
    Email
  },
  data () {
    return {
      mode: 'dark'
    }
  }
}
</script>

<style>
.wave {
  animation-name: wave-animation;
  animation-duration: 2.5s;
  transform-origin: 70% 70%;
  display: inline-block;
}

@keyframes wave-animation {
    0% { transform: rotate( 0.0deg) }
   10% { transform: rotate(14.0deg) }
   20% { transform: rotate(-8.0deg) }
   30% { transform: rotate(14.0deg) }
   40% { transform: rotate(-4.0deg) }
   50% { transform: rotate(10.0deg) }
   60% { transform:  rotate(0.0deg) }
  100% { transform:  rotate(0.0deg) }
}

.wave:hover {
  animation-play-state: running;
}

.wave.running {
  animation-play-state: running;
}
</style>

<page-query>
query {
  posts: allArticles(perPage: 3) {
    edges {
      node {
        id
        title
        path
        date
      }
    }
  }
}
</page-query>
