---
layout: page
title: Ostomate
description: an app for ostomy patients
img: /assets/img/stoma_image_annotated.jpg
---


>  Ostomate aims to provide a better technological solution for stoma management. This technology aims to solve stoma care issues patients currently have such as leakage, significant bleeding, pain, anxiety, changes in weight and dependance on caregivers. Ostomate aim to solve such issues with a 3D profile of the stoma so patients can measure their ostomies with high accuracy and have their ostomy supplies be cut to the correct fit.  

Currently, Ostomate is operating out of the UW [Remote Hub Lab](https://rhlab.ece.uw.edu/), of which I am a member. As a part of the technical team, I have been responsible for many aspects related to our mobile application, including development of the app and setting up the backend.

## the frontend
The mobile application is being developed in the Flutter language which is maintained by Google. The main advantage of Flutter is that it allows for Android and iOS versions deployed from the same codebase.

Being a relatively unpopular language, I found that there was not as much content about it compared to something like Swift or React. However, I was still able to find a couple tutorials on Youtube and along with the docs, was able to teach myself as I implemented features for our app.

### obstacles
This was my first real experience with mobile development and made me consider more deeply how the use interacts with an application. Previously, most of my projects were just built in something like Java and any interaction with the program was done through the console. The focus was not at all about providing any sort of user experience, and more to experiment with new algorithms and libraries. Even though I wasn't responsible for the actual UI design, through implementing the UI I was met with considerations about different situations the user might find them in, and how intuitive it would be to navigate through them.

One such problem was that when a user first signs up, they must verify their account with a code sent to their email address. So as you might imagine, I created a screen after the initial signup page where the user verifies their account, and then they are logged into the actual user dashboard. However, there is a problem with this setup: what if the user closes out of the app before they verify their account? Then, the next time the app is opened they are brought to the login/signup page with no way to navigate back to the verfication page. If they try to login, they are met with an error because their account is not yet verified. To fix this, I added code that checks for whether an account is verified or not upon login, and the user is redirected to the verification page if necessary.

I realized that it's the handling of minor errors like this that largely differentiate a pleasant user experience from a frustrating one, and highlights the importance of testing.

## the backend
Overall, figuring out how to setup a backend was the much more confusing part of this project. Before I began working on Ostomate, "the backend" existed in my mind only as a vague place where all the important logic was handled behind the scenes. I was essentially clueless about how it actually functioned, and I would say that there are many concepts I am still unfamiliar with now.

Fortunately, there is a service on AWS called "AWS Amplify" that simplifies part of the process and makes it easy to integrate a couple of services into one setup. So I taught myself the basics of how to use Amplify and began working with it.

So far, I have mostly been working with AWS Cognito, which deals with user authentication. I plan to work on implementing a REST API to allow the user to perform CRUD operations through the app.

Even though I said the backend was more confusing to setup, the actual heavy-lifting related to the backend was connecting it to the mobile app frontend. There were a lot of unexpected errors that resulted in trying to create users and create/modify new database entries which I only figured out after hours of troubleshooting. For this reason, I think it would have been helpful if I had the help of someone more experienced in these technologies, so I could focus on learning the mechanics without worrying about solving random errors that resulted from not knowing how to set it up.

## future steps
The main objective is to continue adding CRUD functionality, and integrate the actual stoma scanning functionality into the app.

## screenshots
{% include figure.html path="assets/img/ostomate-ss-1.png" title="app-screenshot-1" class="img-fluid rounded z-depth-1" width="40%"%}
The main login screen for the Ostomate app.
{% include figure.html path="assets/img/ostomate-ss-2.png" title="app-screenshot-1" class="img-fluid rounded z-depth-1" width="40%" %}
The signup screen for the Ostomate app.
{% include figure.html path="assets/img/dashboard.png" title="app-screenshot-1" class="img-fluid rounded z-depth-1" width="40%" %}
The dashboard menu for the Ostomate app.

