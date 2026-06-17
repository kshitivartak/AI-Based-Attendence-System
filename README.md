# AI-Based-Attendence-System
AI-powered facial recognition attendance system featuring blink-based liveness detection, role-based access control, and a Python/Flask management dashboard.
<img width="822" height="352" alt="image" src="https://github.com/user-attachments/assets/8f33ae70-fd09-4ef0-882b-55edbcaf6ede" />

## The Problem: 
Traditional attendance (manual calling or sign-in sheets) is time-consuming, prone to human error, and easy to fake (proxy attendance). Hardware solutions like Fingerprint scanners are unhygienic, and RFID cards can be shared.
## The Solution: 
A software-based, contactless AI system that uses facial recognition to verify identity and a web dashboard for management.

#### Backend: Python with Flask (Web Framework).
#### Frontend: HTML5, CSS3 (Bootstrap 5), and JavaScript for a responsive UI.
#### Database: SQLite3 (Relational database to handle Users, Subjects, Enrollments, and Logs).
#### AI/Computer Vision
#### OpenCV: For real-time video processing.
#### face_recognition (dlib): To generate 128-dimensional facial embeddings.
#### NumPy: For mathematical operations on image data.

## Core Modules (The Features)
Role-Based Access Control (RBAC): Using Flask decorators to separate Admin (who manages users and subjects) and Teachers (who take attendance and view reports).
Automated Attendance: A live camera feed identifies students and automatically marks them "Present" in the database with a timestamp.
Manual Override: Teachers can manually change a student's status if needed (e.g., if a student arrives late or the camera misses them).
Reporting: A system to generate daily and monthly attendance reports for analysis.

## The AI Logic 
****Facial Recognition:**** It doesn't just "match images." It converts faces into 128-d numerical vectors (embeddings). When a student stands before the camera, it compares their current vector against the stored database using a distance threshold.
****Liveness Detection (Anti-Spoofing):**** To prevent someone from showing a photo of a student to the camera, you implemented Blink Detection.
****Technical Term to Mention:**** EAR (Eye Aspect Ratio). Using dlib’s 68-point landmark model, the system calculates the ratio of the eye opening. A sudden drop in EAR signifies a blink, proving the subject is a living person, not a photo.

<img width="884" height="427" alt="image" src="https://github.com/user-attachments/assets/44bd5baf-59ea-40ff-9f7f-9aa485fb19c9" />
<img width="884" height="434" alt="image" src="https://github.com/user-attachments/assets/3fd48f44-70c7-43d7-a5cc-4b684c86bf78" />
<img width="897" height="359" alt="image" src="https://github.com/user-attachments/assets/63b2f9d4-e5d2-417c-8d3e-67669fa46b8c" />
<img width="900" height="385" alt="image" src="https://github.com/user-attachments/assets/c0612f9a-4657-4dc0-8bde-77c8366a0b84" />
<img width="903" height="497" alt="image" src="https://github.com/user-attachments/assets/871b5a71-1b60-44f5-a316-b1223d045d3a" />
<img width="907" height="550" alt="image" src="https://github.com/user-attachments/assets/590eda63-c145-42b4-aab6-bd65e3cb0489" />
<img width="907" height="287" alt="image" src="https://github.com/user-attachments/assets/a037ee28-3c77-440d-b048-bae387c01da5" />
<img width="913" height="446" alt="image" src="https://github.com/user-attachments/assets/11bc44f1-ec74-4e16-9af7-678e5e066947" />
