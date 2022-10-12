## Welcome to Content Lense 👋

<p align="center">
  <img src="https://user-images.githubusercontent.com/15559708/195378979-701254fa-ada7-41d4-abc7-494a40207a6d.png" />
</p>

Content lense enables bloggers and publishers to analyse their digital content and generate exciting insights.

There are three main parts of this project: the `frontend`, the `API backend` and several `analytics microservices` (e.g. sentiment or mentioned people)

![architecture](https://user-images.githubusercontent.com/15559708/195382078-32a976dd-9ed6-465f-a208-395a9ec86b02.png)

## How to get started

- We will soon provide a very simple docker compose stack that includes latest stable builds of all parts of content lense. You will then just need to do a `docker compose up` to get up and running.
- If you want to try content lense right now, please do the following:
```bash
# Checkout and start the API
git clone git@github.com:content-lense/content-lense-api.git
cd content-lense-api
docker compose up -f
./dev_flush_db.sh
cd ..
# Checkout and start the frontend
git clone git@github.com:content-lense/content-lense-frontend.git
pnpm install
pnpm dev &&
cd ..
# Checkout and start the mention API
git clone git@github.com:content-lense/content-lense-mention-api.git
docker build -f Docker/Dockerfile -t content-lense-mentions:latest .
docker run -it --rm -p 5000:5000 content-lense-mentions

# Open the frontend at https://localhost and login using the admin credentials

- User `admin@cl.com` and password `demodemo`
- OR set the `x-auth-token` to fixture value of `33973585cd5f17cad05f1a09bb663f89`

```




### The API backend (content-lense-api)
https://github.com/content-lense/content-lense-api

Handles authentication, manages data and importing content. This is based on the amazing [api-platform](https://github.com/api-platform/api-platform) project.


### Frontend (content-lense-frontend)
https://github.com/content-lense/content-lense-frontend

React GUI to manage configuration, manage imported data and visualize insights.
  

### Analysis Microservices (content-lense-analysis)

Currently, we plan to implement the following microservices:

- Sentiment analytics (rates imported text by sentiment)
- Mentioned entites (currently, mentioned people are analyzed and enriched with wiki data information such as age or gender)
- Text complexity (using WienerSachtextformel)


## License

This product is licensed MIT-alike with the following restriction:

- While you are more than welcome to use content lense for your own business, you may not provide a commercial cloud service for other end users (your customers).
- We basically want to achive the same legal background as Sentry. We love their product, we love that we can use it for free - that is why there should be protections from other companies selling work without giving back.


<!--
**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->


## Supported by

Media Tech Lab [`media-tech-lab`](https://github.com/media-tech-lab)

<a href="https://www.media-lab.de/en/programs/media-tech-lab">
    <img src="https://raw.githubusercontent.com/media-tech-lab/.github/main/assets/mtl-powered-by.png" width="240" title="Media Tech Lab powered by logo">
</a>
