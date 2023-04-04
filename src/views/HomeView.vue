<script setup>
import PortfolioItem from "../components/PortfolioItem.vue";
</script>

<template>
  <main>
    <header class="header">
      <div class="header__background-img"></div>
      <div class="header__tint"></div>
      <h1>Jason Gill</h1>
    </header>
    <h2 class="section-title">Projects</h2>
    <PortfolioItem :item="items[0]">
      <template #description>
        <div>
          <h3>Intro</h3>
          <div class="project__description-content">
            <p>
              Carrick-on-Shannon & District Credit Union's previous website was
              a 10-year-old Wordpress site that was showing its age and lacked
              up-to-date content. Having worked with the credit union in other
              areas, I was approached about revamping its web presence by
              developing a new website.
            </p>
          </div>
        </div>
        <div>
          <h3>Task</h3>
          <div class="project__description-content">
            <p>
              I began by visiting the websites of many different credit unions
              from Ireland and abroad and put together a specification for the
              new website. I created a prototype using Adobe XD. One key focus
              of the design was to ensure ease of use when updating content.
              This is important so that the website can promote new loan rates,
              special promotions and the latest news. To accomplish this, I
              implemented a single source of truth strategy to ensure data
              doesn't need to be changed in many places every time an update is
              required. I wrote the code for the website using the frontend
              JavaScript framework Vue.js. I provided my colleagues and the
              Board of Directors with frequent updates and development previews
              of the website. In return, I received valuable feedback.
            </p>
          </div>
        </div>
        <div>
          <h3>Challenges</h3>
          <div class="project__description-content">
            <p>
              Developing the website presented some challenges. I had to reach
              out to various IT companies to gain access to our website backend
              as it was not immediately clear who was hosting it. Additionally,
              the website has some text-heavy content. I had to strike a balance
              to ensure information was presented in a clear manner without
              overloading the user. To do so, I implemented a
              documentation-style Info Centre so all the core information is
              presented in the same general area of the site and is split up
              into sections.
            </p>
          </div>
        </div>
        <div>
          <h3>Result</h3>
          <div class="project__description-content">
            <p>
              The new website is now complete and has been approved by the
              Board. It offers users plenty of useful information as well as a
              loan calculator and loan enquiry form. It will go live within the
              near future.
            </p>
          </div>
        </div>
      </template>
    </PortfolioItem>
    <PortfolioItem :item="items[1]">
      <template #description>
        <div>
          <h3>Intro</h3>
          <div class="project__description-content">
            <p>
              During Transition Year, I was asked to develop a website to
              showcase my school's Erasmus participation. The purpose of this
              project was to allow LCA students to document their experiences
              while taking part in the Erasmus programme. The site also had to
              provide information about the school's participation in the
              programme.
            </p>
          </div>
        </div>
        <div>
          <h3>Task</h3>
          <div class="project__description-content">
            <p>
              I worked with another student to develop a custom WordPress theme.
              They assisted with the UI design and I wrote the code. This
              provided me with a great opportunity to enhance my PHP skills by
              learning more about the workings of the WordPress CMS. The website
              features a blog which allows students to write about their
              experiences. In addition to this, there are various pages of
              information about the programme. The school's Erasmus coordinator
              provided some PDF documents to me containing further information,
              which I then uploaded to the website. Some of these documents were
              uploaded to a dedicated Partners page, which provided content from
              some of the school's partner institutions.
            </p>
          </div>
        </div>
        <div>
          <h3>Result</h3>
          <div class="project__description-content">
            <p>
              The website was completed successfully. The LCAs students were
              provided with log in details which allowed them to write daily
              reports about their time on the Erasmus programme. They wrote blog
              posts with a mix of text content and pictures. In addition,
              details about the school's Erasmus programme were organised in one
              place and easily accessible.
            </p>
          </div>
        </div>
      </template>
    </PortfolioItem>
    <PortfolioItem :item="items[2]">
      <template #description>
        <div>
          <h3>Intro</h3>
          <div class="project__description-content">
            <p>
              I've had a long interest in aviation and began researching flight
              tracking a few years ago. Since then, I have put together various
              setups, each building on the previous. I began with a simple
              RTL-SDR USB and a small indoor antenna. I used software such as
              Virtual Radar Server which displays the tracked aircraft on a map.
              I built a web app that linked a database of my aviation photos to
              the tracked aircraft.
            </p>
          </div>
        </div>
        <div>
          <h3>Task</h3>
          <div class="project__description-content">
            <p>
              I wanted to begin feeding the data I was collecting to the popular
              flight tracking website flightradar24.com. To do this, I put
              together a new setup, consisting of the following hardware
              components:
            </p>
            <ul>
              <li>Raspberry Pi Model B</li>
              <li>Flirc case to keep temperatures lower</li>
              <li>FlightAware Pro Stick Plus</li>
              <li>jetvision A3 ADS-B antenna (1090 MHz)</li>
            </ul>
            <p>On the software side, I am using the following:</p>
            <ul>
              <li>readsb - an ADS-B decoder</li>
              <li>
                tar1090 - runs a local web server and allows me to see the
                tracked aircraft on a map. Keeps a local log of the past 8 hours
                of traffic.
              </li>
              <li>fr24feed - feeds data to Flightradar24</li>
            </ul>
          </div>
        </div>
        <div>
          <h3>Result</h3>
          <div class="project__description-content">
            <p>
              The setup feeds data to Flightradar24 24/7 as radar EISG2. It
              tracks around 700 aircraft per day, with a maximum range of 140 nm
              (259 km). On average, 100,000 messages are received from tracked
              aircraft each day.
            </p>
          </div>
        </div>
      </template>
    </PortfolioItem>
  </main>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          name: "Carrick-on-Shannon & District Credit Union",
          date: "August 2022",
          madeWith: "vue,sass",
          url: "http://carrickcreditunion.com/",
          logoUrl: "coscu-logo-new-blue-alt.png",
          imagesFolder: "coscu",
          images: [
            {
              src: "home.jfif",
              caption: "Home page",
              primary: true,
            },
            {
              src: "resources.jfif",
              caption: "Forms & downloads",
              primary: true,
            },
            {
              src: "membership.jfif",
              caption: "Membership page in Info Centre",
            },
            {
              src: "loanEnquiry.jfif",
              caption:
                "Loan enquiry form - submitted to credit union directly by email",
            },
            {
              src: "exploreLoans.jfif",
              caption: "Explore loans page listing all available loan rates",
            },
          ],
        },
        {
          name: "Carrick CS Internationalization",
          date: "May 2019",
          madeWith: "wordpress",
          url: "https://internationalization.blog/",
          logoUrl: "crest.png",
          imagesFolder: "internationalization",
          images: [
            {
              src: "home.jfif",
              caption: "Home page",
              primary: true,
            },
            {
              src: "blog-post.jfif",
              caption: "Sample blog post written by a student",
              primary: true,
            },
            {
              src: "partners.jfif",
              caption: "Partner institutions",
            },
            {
              src: "erasmus.jfif",
              caption: "Erasmus programme information",
            },
            {
              src: "blog.jfif",
              caption: "Student-written blog",
            },
          ],
        },
        {
          name: "Flightradar24 ADS-B / Mode S data provider",
          date: "July 2022",
          madeWith: "readsb,tar1090,pi,",
          url: "https://www.flightradar24.com/share-statistics",
          imagesFolder: "fr24",
          images: [
            {
              src: "setup.jpg",
              caption:
                "Raspberry Pi 4 Model B in Flirc case, FlightAware Pro Stick Plus, FlightAware 1090 MHz ADS-B Bandpass SMA Filter",
              primary: true,
            },
            {
              src: "setup-2.png",
              caption: "jetvision A3 ADS-B antenna (1090 MHz)",
              primary: true,
            },
          ],
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.header {
  padding: 6em 4em;
  margin-bottom: 3em;
  position: relative;
  text-align: center;
  user-select: none;
  // color: #fff;
  border: 20px solid var(--dark-grey);
  background-size: cover;
  background-position: center;
  h1 {
    font-size: 6em;
    font-weight: bold;
    text-transform: uppercase;
    display: inline-block;
  }
  &__background-img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-position: center;
  }
  &__tint {
    background: url("/grid.png");
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }
}
.section-title {
  margin: 3.5em 0 1em;
  text-transform: uppercase;
  letter-spacing: -2px;
  font-size: 3.5em;
  text-align: center;
  user-select: none;
}
@media (max-width: 600px) {
  .header {
    h1 {
      font-size: 4em;
    }
  }
}
</style>
