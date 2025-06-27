# fitball-fierce-waitlist name: Deploy to Firebase Hosting

on:
  push:
    branches:
      - main

jobs:
  build:
    name: Build & Deploy
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - uses: FirebaseExtended/action-hosting-deploy@v0
        with:
          repoToken: "${{ secrets.GITHUB_TOKEN }}"
          firebaseServiceAccount: "${{ secrets.FIREBASE_SERVICE_ACCOUNT }}"
          channelId: live
          projectId: fitballfierce
