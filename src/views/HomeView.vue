<template>
  <div class="home">
    <div class="job-list">
      <!-- Tidak dilanjutkan karena API tidak bisa diakses -->
      <!-- <div v-for="job in jobs" :key="job.id" class="job">
        <span class="job-title">{{ job.title }}</span>
        <button @click="toggleJobDetail(job)">See Job</button>
      </div> -->

      <div class="job">
        <span class="job-title">Marketing Planner</span>
        <button @click="toggleJobDetail">See Job</button>
      </div>
      <div class="job">
        <span class="job-title">UI/UX Content Creator</span>
        <button @click="toggleJobDetail">See Job</button>
      </div>
      <div class="job">
        <span class="job-title">HR/Legal Manager</span>
        <button @click="toggleJobDetail">See Job</button>
      </div>
      <div class="job">
        <span class="job-title">UI/UX Designer</span>
        <button @click="toggleJobDetail">See Job</button>
      </div>
      <div class="job">
        <span class="job-title">Java Spring Boot</span>
        <button @click="toggleJobDetail">See Job</button>
      </div>
      <div class="job">
        <span class="job-title">Java Spring Boot</span>
        <button @click="toggleJobDetail">See Job</button>
      </div>
    </div>
    <div class="job-detail-wrapper">
      <div class="job-detail" v-if="jobDetail">
        <h1>Marketing Planner</h1>

        <div class="job-desc">
          <h3>Job Description :</h3>
          <ul>
            <li>
              Monitor competition to identify new industry trends and
              opportunities for innovation
            </li>
            <li>
              Develop marketing strategies based on customer preferences,
              bussiness objectives, and available resources
            </li>
            <li>
              Conduct market research to identify potential customers and assess
              their needs, interest, and preferences
            </li>
            <li>
              Work with design teams to develop marketing materials such as
              brochures, ads, and presentation
            </li>
            <li>
              Create an advertising budget that reflects the company's
              priorities while remaining within the parameters set buy upper
              management
            </li>
            <li>
              Develop an effective communication strategies for each campaign
              using several different channels, including social media, email,
              push notifications, print ads
            </li>
            <li>
              Create a detailed timeline of all marketing activities, including
              production schedules, deadlines for materials delivery, and event
              dates and locations
            </li>
            <li>
              Provide feedback to superiors regarding the effectiveness of new
              campaigns and recommend adjustmens
            </li>
          </ul>
        </div>

        <div class="job-skill">
          <h3>Skill :</h3>
          <ul>
            <li>Minimum bachelor degree in Marketing Management</li>
            <li>
              Minimum 3-5 years experience as Marketing Manager/Director in any
              marketplace industry
            </li>
            <li>Good time management and project management skills</li>
            <li>Creative communication skill in both verbal and design</li>
            <li>Multi-language abilities in verbal and non-verbal</li>
          </ul>
        </div>

        <div class="job-apply-form">
          <h3>Send Your Job Application</h3>
          <form class="form">
            <div class="input-box name">
              <label for="name">Your Name</label>
              <input type="text" name="name" placeholder="Enter your name" />
            </div>
            <div class="input-box mobile">
              <label for="mobile">Mobile Number</label>
              <input
                type="text"
                name="mobile"
                placeholder="Enter your mobile number"
              />
            </div>
            <div class="input-box email">
              <label for="email">Email Address</label>
              <input type="email" name="email" placeholder="Enter your email" />
            </div>
            <div class="input-box msg">
              <label for="msg">Write your message here...</label>
              <input type="text" name="msg" placeholder="Enter your message" />
            </div>
            <div class="input-box file">
              <label for="file">File</label>
              <input type="file" />
              <div class="custom-file">
                <img src="../assets/upload.png" width="20" />
              </div>
            </div>
          </form>
          <button>Send Message</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
// import axios from "axios";

export default {
  setup() {
    const jobs = ref([]);
    const selectedJob = ref(null);
    const jobDetail = ref(true);
    const toggleJobDetail = () => {
      jobDetail.value = !jobDetail.value;
    };

    // Tidak dilanjutkan karena API tidak bisa diakses
    // const toggleJobDetail = (job) => {
    //   selectedJob.value = job;
    // };

    // const getJobData = async () => {
    //   try {
    //     const response = await axios.get(
    //       "https://bti.id/services/btiportalcorems/api/pt-job-posts/no-auth"
    //     );
    //     jobs.value = response.data;
    //   } catch (error) {
    //     console.error("Error fetching data:", error.message);
    //   }
    // };

    // onMounted(() => {
    //   getJobData();
    // });

    return {
      jobs,
      selectedJob,
      jobDetail,
      toggleJobDetail,
    };
  },
};
</script>

<style>
.home {
  width: 100%;
  padding: 20px;
}

.job-list {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
  /* width: 100%; */
}

.job {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 500px;
  background-color: rgb(239, 237, 232);
  padding: 10px 20px;
  border-radius: 10px;
  color: green;
  font-weight: 700;
  box-shadow: 1px 6px 16px -4px rgba(0, 0, 0, 0.75);
}

.job button {
  background-color: rgb(245, 165, 68);
  border: none;
  padding: 10px;
  color: #fff;
  border-radius: 10px;
  font-weight: 600;
  cursor: pointer;
}

.job-detail-wrapper {
  /* width: auto; */
  margin: 20px 150px;
  display: flex;
  justify-content: center;
}

.job-detail {
  background-color: rgb(239, 237, 232);
  padding: 50px;
  width: auto;
  border-radius: 10px;
}
.form {
  display: flex;
  flex-wrap: wrap;
}

.job-detail h3 {
  margin: 20px 0;
}

.job-detail ul {
  margin-left: 30px;
}

.input-box {
  display: flex;
  flex-direction: column;
  width: 50%;
  gap: 5px;
  margin-bottom: 20px;
}

.input-box label {
  font-weight: 600;
}

.input-box input {
  /* width: 60%; */
  background: none;
  border: none;
  border-bottom: 1px solid rgb(176, 176, 176);
  margin-top: 10px;
  margin-right: 10px;
}

.input-box input:focus {
  outline: none;
}

.input-box:last-child input {
  border-bottom: none;
  opacity: 0;
  position: relative;
  top: 35px;
  z-index: 9999;
  cursor: pointer;
}

.input-box.file {
  position: relative;
}

.custom-file {
  background-color: rgb(222, 147, 57);
  width: 80px;
  height: 80px;
  border-radius: 10px;
  position: absolute;
  top: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.job-apply-form button {
  margin-top: 50px;
  background-color: rgb(135, 135, 135);
  color: #fff;
  border-radius: 10px;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
}

/* @media only screen and (max-width: 768px) {

} */
</style>
