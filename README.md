# Simple Notes App
This is a simple notes app which built with React and Django.
in this we can add the our important note or also we can use this as to do list app

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/Satankumaryadav/Note-App.git
```

2. Build the app
```
docker build -t note-app-sky1 .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`
