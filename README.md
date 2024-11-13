# shivraj-hood
this is my level 2 task 2  internship of codsoft  


  THIS IS HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Job Application Platform</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Welcome to Our Job Platform</h1>
    <input type="text" id="searchBar" placeholder="Search for jobs...">
  </header>

  <main>
    <section id="jobListings">
      <h2>Job Listings</h2>
      <div class="job" data-id="1">
        <h3>Front-End Developer</h3>
        <p>Company: Tech Solutions</p>
        <p>Location: Remote</p>
      </div>
      <div class="job" data-id="2">
        <h3>UX Designer</h3>
        <p>Company: Creative Agency</p>
        <p>Location: New York, NY</p>
      </div>
      <div class="job" data-id="3">
        <h3>Full Stack Developer</h3>
        <p>Company: Creative Agency</p>
        <p>Location: New York, NY</p>
      </div>
      <div class="job" data-id="4">
        <h3>Software Developer</h3>
        <p>Company: Creative Agency</p>
        <p>Location: New York, NY</p>
      </div>
    </section>

    <section id="jobDetails" style="display: none;">
      <h2>Job Details</h2>
      <div id="detailsContent"></div>
      <button id="backToListings">Back to Listings</button>
    </section>
  </main>
  <footer>
    <div class="footer-content">
      <p>&copy; 2024 Job Application Platform. All rights reserved.</p>
      <div class="footer-links">
        <a href="#">Privacy Policy</a>
        <a href="#">Terms of Service</a>
        <a href="#">Contact Us</a>
      </div>
    </div>
  </footer>
  

  <script src="app.js"></script>
</body>
</html>

THIS IS CSS CODE



body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

header {
  background-color: #4693e0;
  color: white;
  padding: 1rem;
  text-align: center;
}

#searchBar {
  margin-top: 1rem;
  padding: 0.5rem;
  width: 50%;
}

main {
  padding: 2rem;
  background-color: rgba(223, 255, 239, 0.667);
}

.job {
  border: 1px solid #000000;
  background-color: azure;
  padding: 1rem;
  margin: 1rem 0;
  cursor: pointer;
}

#jobDetails {
  margin-top: 2rem;
}
footer {
  background-color: #4693e0;;
  color: #fff4f4;
  text-align: center;
  padding: 1.5rem 0;
  margin-top: 2rem;
}

.footer-content {
  max-width: 800px;
  margin: 0 auto;
}

.footer-links {
  margin-top: 0.5rem;
}

.footer-links a {
  color: #f0fbff;
  margin: 0 1rem;
  text-decoration: none;
}

.footer-links a:hover {
  text-decoration: underline;
}



THIS IS JAVASCRIPT


document.addEventListener('DOMContentLoaded', () => {
    const jobListings = document.querySelectorAll('.job');
    const jobDetailsSection = document.getElementById('jobDetails');
    const detailsContent = document.getElementById('detailsContent');
    const backToListingsButton = document.getElementById('backToListings');
  
    const jobData = {
      1: {
        title: 'Front-End Developer',
        company: 'Tech Solutions',
        location: 'Remote',
        description: 'Develop user-friendly web applications using modern JavaScript frameworks.',
        requirements: '2+ years of experience in front-end development, proficient in React.js.'
      },
      2: {
        title: 'UX Designer',
        company: 'Creative Agency',
        location: 'New York, NY',
        description: 'Design engaging user experiences for web and mobile applications.',
        requirements: '3+ years of experience in UX design, strong portfolio required.'
      },
      3: {
        title: 'Full Stack Developer',
        company: 'Google',
        location: 'Bengaluru',
        description: 'Google remains a tech giant, and its commitment to innovation makes it an exciting destination for full-stack developers. With projects ranging from Android development to cloud services, Google offers a diverse playground for those adept at both front-end and back-end technologies..',
        requirements: '2+ years of experience in front-end development, proficient in React.js.'
      },
      4: {
        title: 'Software Developer',
        company: 'ThoughtWorks',
        location: ' pune',
        description: 'Develop user-friendly web applications using modern JavaScript frameworks.',
        requirements: '4+ years of experience in front-end development, proficient in React.js.'
      }
    };
  
    jobListings.forEach(job => {
      job.addEventListener('click', () => {
        const jobId = job.getAttribute('data-id');
        const jobInfo = jobData[jobId];
        detailsContent.innerHTML = `
          <h3>${jobInfo.title}</h3>
          <p><strong>Company:</strong> ${jobInfo.company}</p>
          <p><strong>Location:</strong> ${jobInfo.location}</p>
          <p><strong>Description:</strong> ${jobInfo.description}</p>
          <p><strong>Requirements:</strong> ${jobInfo.requirements}</p>
        `;
        jobDetailsSection.style.display = 'block';
        document.getElementById('jobListings').style.display = 'none';
      });
    });
  
    backToListingsButton.addEventListener('click', () => {
      jobDetailsSection.style.display = 'none';
      document.getElementById('jobListings').style.display = 'block';
    });
  
    // Basic search functionality
    document.getElementById('searchBar').addEventListener('input', (event) => {
      const searchTerm = event.target.value.toLowerCase();
      jobListings.forEach(job => {
        const jobTitle = job.querySelector('h3').textContent.toLowerCase();
        job.style.display = jobTitle.includes(searchTerm) ? 'block' : 'none';
      });
    });
  });
  
