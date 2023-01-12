# BrainIN - SMART_ATTENDENCE_APP_SIH_2022
This is an Android Application developed for Smart India hackathon 2022 Programme.<br />
It's an Smart Attendance App that is powered by face recognition technology.<br />
The UI/UX is really simple and self explanatory, the user will not face any issues.<br />

## 💻 Tech Stack used 
- **Java** - Developed using Android studio and Java as developing Language
- **Figma** - [**Designed using Figma**](https://www.figma.com/file/jjNrOhXOxz2nnSpAYamNsA/PresIN-Engage?node-id=107%3A21)
- **XML** - To implement design into code
- **Firebase** - To authenticate users, store user's data and perform operations and store files (PDFs)
- **ML Kit** - To detect faces in the application [ML Kit - Firebase](https://developers.google.com/ml-kit)
- **TensorFlow Lite** - To recognize Faces [TensorFlow Lite](https://www.tensorflow.org/lite)
- **Pre-Trained model** - [MobileFaceNet](https://github.com/sirius-ai/MobileFaceNet_TF)
- **CameraX** - To capture faces and recognize using camera preview [CameraX](https://developer.android.com/training/camerax)

## ✨ Features
- **Face Recognition** - Makes it an MVP app
- **Attendees list** - Shows a list of attendees that are present on that particular day
- **Progress** - To check the monthly attendance progress and consistency
- **PDF** - Admin can add PDFs and anyone can download it, comes in handy when sharing important pdfs, previours year papers and so on
- **Settings/Profile/Edit profile** - Check your current details and also get the access to edit your profile.

## ❓ How to use the app?
- Create an account -> Register by adding your face and all the required details asked (Login as Admin to test all the features)
- Verify your Email
- Signin to your account and mark your attendance.
- Follow this video for reference - <br />
- **Important** (Before deleteing your account from Firebase Authentication, logout first and delete the Firebase Realtime Database of your userID Node)

## 🤔 How it works?
- Intialially during registration the user's face embeddings is stored in a HashMap as value with a key that is same of all users "added".<br />
- Then after signin in, the key "added" is replaced with the userID -> <UserID, Embeddings> and stored in the user's Node<br />
- These node from users is then used during facial recognition<br />
- During facial recognition, the embeddings obtained from the person in the camera is used to calculate the euclidean distance between the person and the list of embeddings in the Firebase   RealTime Database.<br />
- If the distance is less than 1.0f and also the Key -> userID of the same hashmap is matched with the current logged in userID then it is success, the attendance is marked.<br />

## Flow of the Application
![PresIN](https://user-images.githubusercontent.com/62587060/170339689-8665f94f-f158-4717-80b1-8713251e6bc8.png)

## 📝 License

```
MIT License

Copyright (c) 2022 BrainIn

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)
![ForTheBadge ANDROID](https://forthebadge.com/images/badges/built-for-android.svg)
![ForTheBadge GIT](https://forthebadge.com/images/badges/uses-git.svg)
