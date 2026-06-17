# AI-Based-Attendence-System
AI-powered facial recognition attendance system featuring blink-based liveness detection, role-based access control, and a Python/Flask management dashboard.

## The Problem: 
Traditional attendance (manual calling or sign-in sheets) is time-consuming, prone to human error, and easy to fake (proxy attendance). Hardware solutions like Fingerprint scanners are unhygienic, and RFID cards can be shared.
## The Solution: 
A software-based, contactless AI system that uses facial recognition to verify identity and a web dashboard for management.

### Backend: Python with Flask (Web Framework).
### Frontend: HTML5, CSS3 (Bootstrap 5), and JavaScript for a responsive UI.
### Database: SQLite3 (Relational database to handle Users, Subjects, Enrollments, and Logs).
### AI/Computer Vision
### OpenCV: For real-time video processing.
### face_recognition (dlib): To generate 128-dimensional facial embeddings.
### NumPy: For mathematical operations on image data.

## Core Modules (The Features)
Role-Based Access Control (RBAC): Using Flask decorators to separate Admin (who manages users and subjects) and Teachers (who take attendance and view reports).
Automated Attendance: A live camera feed identifies students and automatically marks them "Present" in the database with a timestamp.
Manual Override: Teachers can manually change a student's status if needed (e.g., if a student arrives late or the camera misses them).
Reporting: A system to generate daily and monthly attendance reports for analysis.

## The AI Logic 
****Facial Recognition:**** It doesn't just "match images." It converts faces into 128-d numerical vectors (embeddings). When a student stands before the camera, it compares their current vector against the stored database using a distance threshold.
****Liveness Detection (Anti-Spoofing):**** To prevent someone from showing a photo of a student to the camera, you implemented Blink Detection.
****Technical Term to Mention:**** EAR (Eye Aspect Ratio). Using dlib’s 68-point landmark model, the system calculates the ratio of the eye opening. A sudden drop in EAR signifies a blink, proving the subject is a living person, not a photo.
