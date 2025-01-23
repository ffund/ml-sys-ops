---
title: Machine Learning Systems Engineering and Operations
layout: home
nav_order: 1
---

# ECE-GY 9183 Machine Learning Systems Engineering and Operations - Spring 2025

_Fraida Fund_ 

**Description**: Building deployable, reliable, and scalable machine learning systems involves a lot more than just training a model. In this graduate course on machine learning systems engineering and machine learning operations (MLOps), students will learn techniques for designing, developing, evaluating, deploying, monitoring, and updating production-ready machine learning systems at scale. 

**Instructor**: Fraida Fund (ffund@nyu.edu) (370 Jay St, Room 936). The best way to reach me is to post on Ed or to visit my office hour (see Brightspace calendar for dates and Zoom links).

**Instruction mode**: In person. We will meet on Thursdays at 2PM in 370 Jay Street, Room 202.

**Prerequisites**: ECE-GY 6143 Intro ML or equivalent.

**Approach**: students will learn through a combination of lectures, case studies, guided lab assignments on the [ChameleonCloud](https://chameleoncloud.org/) research infrastructure and on commercial clouds (GCP, AWS), and a final project.

**Grading**: 60% lab assignments (weekly); 40% final project.

**Relationship to other ECE courses**: Although only Intro ML is required as a prerequisite, this course will complement existing ECE courses at NYU Tandon (for students who have taken/will take them), including 

* ML courses such as ECE-GY 6143 Intro to Machine Learning, ECE-GY 7123 Deep Learning, and ECE-GY 9143 Intro to High Performance Machine Learning
* and networking/systems courses such as ECE-GY 6353 Internet Architecture and Protocols and ECE-GY 6363 Data Center and Cloud Computing.

Prior/future experience in any of the above is helpful, although not necessary (except for Intro ML). Students will gain a big-picture view and hands-on experience integrating concepts from all of these courses into the development of a production-ready machine learning system. 

**Topics**: This course will cover the following topics (tentative plan/subject to change):

1. Challenges and basic principles of machine learning systems engineering and operations.
2. Overview of cloud computing.
3. DevOps and continuous X for ML systems (integration, training, deployment, testing, monitoring).
4. Model training at scale.
5. Scheduling training jobs; versioning and reproducibility.
6. Model serving.
7. Monitoring and evaluating ML systems.
8. Large scale data systems.
9. Using commercial clouds (GCP, AWS).

The remaining lecture sessions will be used for case studies, additional topics, and project presentations.

**Time commitment**: This is a 3-credit course. The average student should spend at least 3 hours/week/credit → 9 hours/week for a 3 credit course. A typical week will include:

- lecture: 2-2.5 hours
- reading for additional depth (case study/academic paper): 1 hour
- lab assignment: 4-5 hours

as well as some time for project development and implementation. (Toward the end of the semester, the lab workload will decrease somewhat to allow more time for project work.) A student who is not very comfortable with computer systems may have to spend more time than the estimate above in order to do well. 

**Compute resources**: For most lab assignments and the course project, students will use storage, network, and compute resources on [ChameleonCloud](https://chameleoncloud.org/), including bare metal GPU instances, virtual machines, and containers on edge devices. We will also use [GCP](https://cloud.google.com/gcp) for one lab assignment (coupons will be available for GCP credit; you will not need a credit card to sign up).

To make sure that compute resources will be available to all students in the course: students are expected to use these resoures for this course *only*, not for personal projects or other courses; and to follow guidelines regarding usage when specified.

**Final project**: The final project will be a group project, completed in groups of 3 or 4. Refer to the [Project](docs/project) page for more details on specific requirements.

**Policy on late work**: Lab assignments will be released on Fridays, and will be due on Thursdays at midnight. However, the "due date" is not the "do date" - you should plan to complete each lab early, so that if you need help or encounter unexpected problems (illness, technical issues, etc.) you will still have time to re-do it before the deadline. 

This is especially important because we have a limited quota for compute resources, and it is simply not possible in many cases for the entire class to do the lab assignment on the day that it is due. In some cases, you will have to reserve a time slot to use scarce compute resources, or be assigned to specific days on which you may access the compute resources.

However, in recognition of the fact that 

1. you can't work on these labs progressively over the course of the week - you're going to plan to do them all in one sitting while you have the infrastructure set up, and 
2. last-minute problems (had an interview, overslept, laptop died) may prevent you from working on a lab at the time you had planned,

you get 72 hours of "free" late time to use on lab assignments in this course. You should not *plan* to do a lab assignment after the deadline, because if you use up your "free" late time and then have an unplanned circumstance later in the course, you'll be stuck. But if you have no choice, you *may* submit a lab assignment late without penalty if you have not yet "used up" your 72 hours. You can use the 72 hours all at once, or you can spread them across multiple assignments (e.g. use 24 hours on one, 48 hours on another).

Once you have accumulated 72 hours of lateness in this course, a penalty of 1/5 of the value of the assignment is applied for each hour of lateness. 

For exceptional circumstances, like a major illness or a family emergency, you may contact the student advocate about an extended deadline on a lab assignment. (See "Illness or other exceptional situations".)

There is no late work accepted for project deliverables.

---

### Academic integrity and collaboration policies

**General policies**: For general academic integrity guidelines, please review the [NYU Tandon Student Code of Conduct](https://engineering.nyu.edu/life-tandon/student-life/student-advocacy/student-code-conduct) (n.b. the academic misconduct section). 

**Course-specific collaboration policy**: For this course in particular:

* Students are expected to do all lab assignments individually. If a student shows or gives any part of his/her work to another student, then both students are considered to be cheating. 
* Projects will be completed as a group, but individual group members are expected to "own" specific parts. Group members are expected to "pull their weight" and to be honest about their individual contributions; if a group member does "your" part for you, and you misrepresent it as your own work, this is considered cheating.

If you need help with a lab assignment, these are the ways in which you are *permitted* to get help from someone else:

* You may ask questions about lab assignments on the Q&A site (Ed). Even though it is visible to the rest of the class, you don't have to worry about "giving away an answer" when asking a question. 
* You can visit an office hour with course staff and ask questions there.
* You may discuss lab assignments with classmates or other people who are not course staff as follows: *without sharing or directly showing your materials* (question, solution, failed attempt, data, figures), you can verbally discuss with other students the approach you used to solve a particular problem. (A useful guideline is: if there is a screen involved in this discussion, it's not allowed.)

But, these ways of getting help are *not permitted*:

* You may not share your lab work with anyone else by email or other private communication channel. (Not even for "comparison", not a partial answer, not a screenshot of your answer, not an incorrect answer, not even a question variant with no answer...) Note that if multiple students submit the same work, they will *all* get a zero.

Also note: 

* After the class ends, some students like to share their solutions to assignments as part of an online "portfolio", to show off their work. However, you may only share the part that you wrote - you may not share the parts of any lab "template" (code or text) that were written by me. In general, the material distributed to you is for your use in this course, and you do not have permission to redistribute it.

**Policy on use of AI**: You are permitted to use AI assistance for the following:

* computer translation between English and another language, e.g. you may write an explanation for a question on a lab assignment in another language and then submit a direct translation to English using Google Translate or a similar service. (Note: this does not include "cleaning up" or rephrasing text, which is not allowed - only direct translation is allowed. You shouldn't "clean up" text because (1) I don't care about your spelling, grammar, or vocabulary, and (2) if I am asking for an open-ended response, I want to hear *your* voice, not an LLM's voice.)
* to generate Python code for plotting and visualization. You are fully responsible for any figures or visualizations you submit, including making sure their appearance is reasonable and the data in them is correct. But, you are permitted to use an AI assistant such as ChatGPT or Gemini to help you generate `matplotlib` or `seaborn` code to make your plots look the way you want. If you do use an AI assistant, you must include your LLM prompt in your submission.

With the exception of the tasks listed above, AI assistance is not permitted in this course.

**Violation of academic integrity policies**: The course staff wants to spend their time and effort supporting students who want to learn, not policing students' avoidance of learning. However, when we *do* detect a violation of these policies, we take it very seriously.

* on the first instance of a violation of these academic integrity policies, a zero grade will be applied for the assessment. Also, a record of the incident will be kept in the Office of Student Life and Services by the Office of Student Advocacy, as described in the [Student Code of Conduct](https://engineering.nyu.edu/life-tandon/student-life/student-advocacy/student-code-conduct).
* on a second instance, an F grade will be assigned for the course. Also, a record of the incident will be kept in the Office of Student Life and Services by the Office of Student Advocacy, as described in the [Student Code of Conduct](https://engineering.nyu.edu/life-tandon/student-life/student-advocacy/student-code-conduct).

By design, the consequence for an academic integrity violation is always worse than the consequence for not knowing an answer - if you don't know an answer to a question, you may earn a zero on just that question. If you violate the academic integrity policies of the course, you will earn a zero on the entire assessment (lab assignment, project, etc). There are no opportunities to "make up" points lost on an assignment due to an academic integrity violation.


---

### Other policies

**Inclusion**: The NYU Tandon School values an inclusive and equitable environment for all our students. I hope to foster a sense of community in this class and consider it a place where individuals of all backgrounds, beliefs, ethnicities, national origins, gender identities, sexual orientations, religious and political affiliations, and abilities will be treated with respect. It is my intent that all students’ learning needs be addressed both in and out of class, and that the diversity that students bring to this class be viewed as a resource, strength and benefit. If this standard is not being upheld, please feel free to speak with me.

**Disability**: If you are student with a disability who is requesting accommodations, please contact New York University’s Moses Center for Students with Disabilities (CSD) at 212-998-4980 or mosescsd@nyu.edu.  You must be registered with CSD to receive accommodations.  Information about the Moses Center can be found at www.nyu.edu/csd. Note for those who require accommodations for timed assessments: this class does not have timed exams.

**Illness or other exceptional situations**: If you are experiencing an illness or any other situation that might affect your academic performance in a class,  please contact the student advocate: https://engineering.nyu.edu/life-tandon/student-life/student-advocacy who will reach out to the course instructor on your behalf for accommodations when warranted. Students who need an excused absence (e.g. an extended deadline on an assignment due to illness) should complete the "Excused Absence" form on the Student Advocacy website.
