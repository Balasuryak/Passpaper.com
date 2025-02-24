<template>
    <div class="courses-page">
      <h1>ALL Courses</h1>
      <div class="courses-grid">
        <div v-for="course in courses" :key="course.id" class="course-box">
          <div class="image-container">
            <img :src="course.image" :alt="course.name" class="course-image" />
          </div>
          <h2>{{ course.name }}</h2>
          <p>{{ course.description }}</p>
          <router-link :to="course.url" class="course-link">
            <button @click="viewCourse(course.name)">Go to course Page</button>
          </router-link>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "CoursesPage",
    data() {
      return {
        courses: [
          {
            id: 1,
            name: "Programming",
            description: "Learn the basics of programming.",
            image:
              "https://images.unsplash.com/photo-1542831371-29b0f74f9713?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80",
            url: "/Dashboard",
          },
          {
            id: 2,
            name: "NEET Exam",
            description: "Prepare for NEET with top resources.",
            image:
              "https://education.sakshi.com/sites/default/files/images/2024/05/04/neet-1714806841.jpg",
            url: "/neetdashboard",
          },
          {
            id: 3,
            name: "JEE Exam",
            description: "Crack JEE with comprehensive guides.",
            image: "https://resize.indiatvnews.com/en/resize/newbucket/1200_-/2019/11/jee-main-2020-1573981748.jpg",
            url: "/jeedashboard",
          },
        ],
      };
    },
    methods: {
      viewCourse(name) {
        alert(`You are redirected to ${name} page`);
        // Navigate to a course details page or perform other actions
      },
    },
  };
  </script>
  
  <style scoped>
  .courses-page {
    padding: 20px;
    text-align: center;
  }
  
  .courses-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 20px;
  }
  
  .course-box {
    border: 1px solid #ccc;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  
  .image-container {
    width: 100%;
    aspect-ratio: 4 / 3; /* Ensures all images have the same aspect ratio */
    overflow: hidden;
    border-radius: 8px;
    margin-bottom: 10px;
  }
  
  .course-image {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Ensures the image fills the container without distortion */
  }
  
  .course-box h2 {
    font-size: 18px;
    margin-bottom: 10px;
  }
  
  .course-box p {
    font-size: 14px;
    color: #555;
  }
  
  .course-box button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 10px;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .course-box button:hover {
    background-color: #0056b3;
  }
  </style>
  