+++
title = 'MIDAS: Educational Database for Native American Tribal Nations'
categories = [ 'Projects' ]
date = 2022-01-05T00:00:00-05:00
draft = false
[[links]]
title = 'U-M Data Science expert volunteers support student learning for Native American tribal nations in Michigan'
website = 'https://midas.umich.edu/impact/supporting-student-learning-for-native-american-tribal-nations-in-michigan/'
[[links]]
title = 'National Science Foundation Civic Innovation Challenge supporting collaborative project between the Little Traverse Bay Bands of Odawa Indians and U-M'
website = 'https://midas.umich.edu/ltbb-2022/'
[[links]]
title = 'Michigan: Little Traverse Bay Bands of Odawa Indians - Capturing Native American Tribal Residents Needs through Better Data and Query Systems'
website = 'https://nsfcivicinnovation.org/awardees/#LTBB'
[[links]]
title = "Map of Michigan's Federally Recognized Tribal Nations"
website = 'https://www.michiganbusiness.org/4a8101/globalassets/documents/tribes_map.pdf'
+++

The second of my two undergraduate research projects was about exploring ways for several Native American Tribal Nations in Michigan to better manage and analyze student data. Seeking to modernize their current systems, education directors from three tribes contacted the Michigan Institute for Data Science (MIDAS). The core objective of the educators was to connect career opportunities to outstanding students based on their academic background and other considerations. Additionally, they wanted to identify students who need more support based on their academic performance. However, their student data was scattered across Excel spreadsheets, older databases, and paper records, with no easy way to join, sort, and query their information. As a result, MIDAS organized a team of four students led by Dr. Tayo Fabusuyi to create a solution that could be used by the tribes.  

I was able to take the lead in development using the skills I learned in my electives: Web Systems, Software Engineering, and Database Management Systems. We held individual meetings with each tribe and began to discuss their needs. By applying the methods for gathering requirements that I learned from my software engineering class, we were able to create a comprehensive set of user stories to guide us on our project. We were also made aware of the mistrust between university researchers and indigenous communities. The tribes wanted to ensure that this project led them to have more data sovereignty, as their data has been historically used to surveil, discriminate, or violate their human rights. Therefore, we were committed to keeping regular correspondence with the tribes in order to be attentive to their needs and concerns. Specifically, we were very mindful to prioritize security above all else throughout the entire project.  

The next phase of the project involved reorganizing their data for the new database. We migrated their relational database to a NoSQL database (MongoDB Atlas). In essence, we converted multiple tables of students, schools, etc., to a single document store that maps students to a document that contains all of their data. After thorough analysis, we decided that the trade off in using more storage was worth it for the gains in flexibility and simplicity. For our middleware, we decided to use NodeJS and ExpressJS since everyone on the team was familiar with JavaScript. Its access to many useful libraries allowed us to minimize code which improved maintainability. After setting up an API to facilitate communication between our frontend and our database, we secured our app by integrating popular libraries to help sanitize inputs, salt/hash passwords, and authorize users.  

Web Systems provided me with the knowledge to set up a robust front end with React, a frontend framework that is popular for its stability. Additionally, its flexibility allowed us to create a highly-interactive dashboard that presented data to educators in a familiar spreadsheet layout. Lastly, we incorporated many features to make our app resilient and future-proof. We added the ability to safely edit the entire database without needing to know MongoDB-specific commands. Additionally, we created a tool to interactively create, update, and delete forms in case their informational needs change down the line.  

During my last semester of college, I was able to deploy our web app and begin user testing. After I graduated, our work was later awarded the Civic Innovation Challenge Stage 1 Planning Grant. The purpose of the grant was to fund ready-to-implement, research-based pilot projects that have the potential for scalable, sustainable, and transferable impact on community-identified priorities. This project was not only deeply rewarding, but also instrumental in landing me a job in a related field. I had plenty of interesting things to talk about at career fairs, which helped lead me to my first position out of college as a web developer.
