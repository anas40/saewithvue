<template>
  <main>
    <div>
      <div class="department-heading" id="zfr5">
        <div>
          <div class="department-heading-box">
            <h1>ZFR5.0</h1>
          </div>
        </div>
      </div>
      
      <!-- chairperson -->
      <section class="firsttier" id="top-member">
        <div>
          <div class="member">
            <div class="member-image">
              <img
                :src="
                  require(`@/assets/team images/team-members/${captain.image}`)
                "
                alt
              />
            </div>

            <div>
              <div class="perse-des">
                <h2>{{ captain.position }}</h2>
                <h4>{{ captain.name }}</h4>
              </div>
            </div>
            <div class="linksofmembers">
              <div v-for="(link, index) in captain.links" :key="index">
                <a :href="link.link">
                  <img
                    v-lazy="require(`@/assets/icons/team_icons/${link.image}`)"
                    :alt="link.name"
                  />
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>
      <!-- other leaders -->
      <section class="second-tier" id="top-member">
        <div v-for="leader in leaders" :key="leader.name">
          <div class="member">
            <div class="member-image">
              <img
                :src="
                  require(`@/assets/team images/team-members/${leader.image}`)
                "
                alt
              />
            </div>

            <div>
              <div class="perse-des">
                <h2>{{ leader.position }}</h2>
                <h4>{{ leader.name }}</h4>
              </div>
            </div>
            <div class="linksofmembers">
              <div v-for="(link, index) in leader.links" :key="index">
                <a :href="link.link">
                  <img
                    v-lazy="require(`@/assets/icons/team_icons/${link.image}`)"
                    :alt="link.name"
                  />
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div v-for="department in departments" :key="department.name">
        <div class="department-heading">
          <div>
            <div class="department-heading-box">
              <h1>{{ department.departmentName }}</h1>
            </div>
          </div>
        </div>

        <section class="firsttier">
          <div>
            <div class="member">
              <div class="member-image">
                <img
                  v-lazy="
                    require(`@/assets/team images/team-members/${department.lead.image}`)
                  "
                  alt
                />
              </div>

              <div>
                <div class="perse-des">
                  <h2>{{ department.lead.position }}</h2>
                  <h4>{{ department.lead.name }}</h4>
                </div>
              </div>
              <div class="linksofmembers">
                <div
                  v-for="(link, index) in department.lead.links"
                  :key="index"
                >
                  <a :href="link.link">
                    <img
                      v-lazy="
                        require(`@/assets/icons/team_icons/${link.image}`)
                      "
                      :alt="link.name"
                    />
                  </a>
                </div>
              </div>
            </div>
          </div>
        </section>

        <section class="second-tier">
          <div v-for="member in department.members" :key="member.name">
            <div class="member">
              <div class="member-image">
                <img
                  v-lazy="
                    require(`@/assets/team images/team-members/${member.image}`)
                  "
                  alt
                />
              </div>

              <div class="details">
                <div class="perse-des-small">
                  <h2>{{ member.position }}</h2>
                  <h4>{{ member.name }}</h4>
                </div>
                <div class="linksofmembers">
                  <div v-for="(link, index) in member.links" :key="index">
                    <a :href="link.link">
                      <img
                        v-lazy="
                          require(`@/assets/icons/team_icons/${link.image}`)
                        "
                        :alt="link.name"
                      />
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>

      <div class="department-heading">
          <div>
            <div class="department-heading-box">
              <h1>Our Former Members</h1>
            </div>
          </div>
        </div>
        <section class="second-tier">
          <div v-for="fmember in fmembers" :key="fmember.name">
            <div class="member">
              <div class="member-image">
                <img
                  v-lazy="
                    require(`@/assets/team images/team-members/${fmember.image}`)
                  "
                  alt
                />
              </div>

              <div class="details">
                <div class="perse-des-small">
                  <h2>{{ fmember.position }}</h2>
                  <h4>{{ fmember.name }}</h4>
                </div>
                <div class="linksofmembers">
                  <div v-for="(link, index) in fmember.links" :key="index">
                    <a :href="link.link">
                      <img
                        v-lazy="
                          require(`@/assets/icons/team_icons/${link.image}`)
                        "
                        :alt="link.name"
                      />
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
    </div>
  </main>
</template>
<script>
export default {
  data() {
    return {

      captain: {
        image: "IMG_20191125_201100.jpg",
        position: "Captain",
        name: "Mohammed Tazeem Khan",
        links: [
          {
            name: "insta",
            image: "insta.png",
            link: "https://www.instagram.com/mohammed_tazeem/?hl=en"
          },
          { name: "email", image: "email.png", link: "mailto:mtkhan@zhcet.ac.in" },
          { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/mohammed-tazeem-34b462189" }
        ]
      },
      leaders: [
      {
        name: "Muhammad Aatif Qazi",
        position: "Vice-Captain",
        image: "IMG_20210217_171704atif - SAE ZHCET.jpg",
        links: [
          {
            name: "insta",
            image: "insta.png",
            link: "https://instagram.com/aatif_qazi?igshid=4l70lh37fh7m"
          },
          { name: "email", image: "email.png", link: "mailto:mohammadaatif99.ma@gmail.com" },
          { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/aatifqazi" }
        ]
      },
      { 
        name: "Meesum Raza Zaidi",
        position: "Manager",
        image: "= - mSAE ZHCET.jpg",
        links: [
          {
            name: "insta",
            image: "insta.png",
            link:
              "https://instagram.com/meesumbilgrami?igshid=p2bx6sq11bcf"
          },
          { name: "email", image: "email.png", link: "mailto:meesumbilgrami@gmail.com" },
          { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/meesum-raza-zaidi-4375ba195" }
        ]
      }
      ],
      departments: [
        {
          departmentName: "Vehicle Dynamics",
          lead: {
            name: "Hammad Qamar",
            position: "Vehicle Dynamics Lead",
            image: "IMG_20191126_235448.jpg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "https://www.instagram.com/ham_mad_hu_/"
              },
              { name: "email", image: "email.png", link: "mailto:hammadqamar3@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/mwlite/in/hammad-qamar-96602016b" }
            ]
          },
          members: [
            {
              name: "MD Kashif Raza",
              position: "Suspension",
              image: "my image - Md Kashif19MEB134.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://www.instagram.com/kashif.abbas44/"
                },
                { name: "email", image: "email.png", link: "mailto:kashifreza44@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/md-kashif-raza-862649207/" }
              ]
            },
            {
              name: "Asjad Ali Khan",
              position: "Brakes",
              image: "IMG_20200317_192025_596 - Asjad Ali Khan 19MEB436 (1).jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://www.instagram.com/asjad_khan_13/"
                },
                { name: "email", image: "email.png", link: "mailto:asjadkhan1303@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/asjad-ali-khan-1877731b3" }
              ]
            }
            // {
            //   name: "Aftaab Alam",
            //   position: "Suspension",
            //   image: "IMG_20191125_200951.jpg",
            //   links: [
            //     { name: "insta", image: "insta.png", link: "#" },
            //     { name: "email", image: "email.png", link: "#" },
            //     { name: "linkedin", image: "linkedin.png", link: "#" }
            //   ]
            // },
            
            
          ]
        },
        {
          departmentName: "Chassis & Aerodynamics",
          lead: {
            name: "Tazeem Khan",
              position: "Chassis lead",
              image: "IMG_20191125_201100.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/mohammed_tazeem?igshid=167to096kjg8u"
                },
                { name: "email", image: "email.png", link: "mailto:khantazeem12@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/mohammed-tazeem-34b462189" }
              ]
          },
          members: [
            {
              name: "Mohammad Ali Gauhar ",
              position: "Frame",
              image: "137 - 19CEB524 Md Ali Gauhar (1).jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/md_aligauhar?igshid=pdig82i4q4ez"
                },
                { name: "email", image: "email.png", link: "mailto:aligauhar16122000@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "http://www.linkedin.com/in/md-ali-gauhar-ba4219195" }
              ]
            },
             {
               name: "Arquam Hashim Siddiqui",
               position: "Ergonomics",
               image: "arquam hashim.jpg",
               links: [
                 { name: "insta", image: "insta.png", link: "https://www.instagram.com/arquam_ibn_hashim/" },
                 { name: "email", image: "email.png", link: "mailto:ahsiddiquie@zhcet.ac.in" },
                 { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/arquam-hashim-siddiquie-13b6b716b" }
               ]
             }
          ]
        },
        {
          departmentName: "Powertrain",
          lead: {
            name: "Muhammad Aatif Qazi",
              position: "Powertrain Lead",
              image: "IMG_20210217_171704atif - SAE ZHCET.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/aatif_qazi?igshid=4l70lh37fh7m"
                },
                { name: "email", image: "email.png", link: "mailto:mohammadaatif99.ma@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/aatifqazi" }
              ]
            
          },
          members: [
            {
              name: "Swarnima Chaudhary",
              position: "Drivetrain",
              image: "IMG_20191125_195909.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/swara_ch_?igshid=1vwg120vuqsxf"
                },
                { name: "email", image: "email.png", link: "mailto:swarnima1710@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/swarnima-chaudhary-54ab87189" }
              ]
            },
            {
              name: "Salman Ahmed",
              position: "Cooling",
              image: "IMG_20200103_164329_Bokeh - Salman Ahmad 19mvb31.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://www.instagram.com/salman_ahm_/"
                },
                { name: "email", image: "email.png", link: "salmanahmad1920@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/salman-ahm-" }
              ]
            }
          ]
        },
        {
          departmentName: "Electronics",
          lead: {
            name: "Mohit Mangal",
            position: "Electronics Lead",
            image: "DSC_7319_2.jpg",
            links: [
              { name: "insta", image: "insta.png", link: "#" },
              { name: "email", image: "email.png", link: "mailto:unimohit300@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/0mngl" }
            ]
          },
          members: [
            
            {
              name: "Kunal Sharma",
              position: "Team Member",
              image: "IMG_20191125_200046.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/kcunalsharma?igshid=1ene441cgnfx8"
                },
                { name: "email", image: "email.png", link: "mailto:kunalsharma.jaipur1999@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/kunal-sharma-b757021a1" }
              ]
            }
          ]
        },
        {
          departmentName: "Management",
          lead: {
            name: "Meesum Raza Zaidi",
              position: "Management Team Lead",
              image: "= - mSAE ZHCET.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/meesumbilgrami?igshid=p2bx6sq11bcf"
                },
                { name: "email", image: "email.png", link: "mailto:meesumbilgrami@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/meesum-raza-zaidi-4375ba195" }
              ]
          },
          members: [
            {
              name: "Arsalan Sartaj",
              position: "Business plan",
              image: "arsalan sartaj.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/arsalan_sartaj?igshid=jnc8hpmmy9ds"
                },
                { name: "email", image: "email.png", link: "mailto:arsalansartaj99@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/arsalan-sartaj-b1a659191" }
              ]
            },
            {
              name: "Mohd Amaan",
              position: "Web Developer",
              image: "amaan.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://www.instagram.com/amaanxalii/"
                },
                { name: "email", image: "email.png", link: "maito:aamaan806@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/amaan07/" }
              ]
            },
            {
              name: "Qazi Mohammad Taha",
            position: "Cost Report",
            image: "IMG_20191125_201205.jpg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "https://instagram.com/the_qmt?igshid=1rehizz3lyxjx"
              },
              { name: "email", image: "email.png", link: "mailto:qazimdtaha@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/qazi-t-297392146" }
            ]
            }
            // {
            //   name: "Vinayak Varshney",
            //   position: "Team Member",
            //   image: "IMG_20191126_235630.jpg",
            //   links: [
            //     { name: "insta", image: "insta.png", link: "#" },
            //     { name: "email", image: "email.png", link: "#" },
            //     { name: "linkedin", image: "linkedin.png", link: "#" }
            //   ]
            // }
          ]
        }
      ],
      fmembers : [
           {
              name: "Sarif Anwar",
              position: "Captain FB2020",
              image: "IMG-20191124-WA0025.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/sarif_zfr?igshid=l1i3eze28tbo"
                },
                { name: "email", image: "email.png", link: "mailto:sarifanwar8266@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/sarif-anwar" }
              ]
            },
            {
              name: "Qazi Mohammad Taha",
            position: "Vice Captian FB2020",
            image: "IMG_20191125_201205.jpg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "https://instagram.com/the_qmt?igshid=1rehizz3lyxjx"
              },
              { name: "email", image: "email.png", link: "mailto:qazimdtaha@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/qazi-t-297392146" }
            ]
            },
           {
              name: "Yogesh Kumar",
              position: "Captain FB2021",
              image: "IMG_20191125_200830.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/invincibleface?igshid=1xwuvvbehip8d"
                },
                { name: "email", image: "email.png", link: "mailto:kryogesh831@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/yogesh-kumar-433414172" }
              ]
            },
            {
              name: "Mohd Suboor Aziz",
            position: "Vice Captain FB2021",
            image: "IMG_20191125_200516.jpg",
            links: [
              {
                name: "insta",
                image: "insta.png",
                link: "https://instagram.com/aziz.suboor?igshid=u6gbqw4qva5j"
              },
              { name: "email", image: "email.png", link: "mailto:aziz.ms52090@gmail.com" },
              { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/mohd-suboor-18b594171" }
            ]
            },
            {
              name: "Burhan Shamsi",
              position: "Manager FB2021",
              image: "IMG_20191130_011434.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/__whateverittakes_?igshid=38uj0roq4jfo"
                },
                { name: "email", image: "email.png", link: "mailto:bmdshamsi@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/md-burhan-shamsi-a182b6171" }
              ]
            },
            {
              name: "Tashif khan",
              position: "V.D Lead FB2020",
              image: "IMG_20191125_201318.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/sartashtic?igshid=p4v0i9b5oxfx"
                },
                { name: "email", image: "email.png", link: "mailto:mohdtashif@zhcet.ac.in" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/mohammad-tashif-431697143" }
              ]
            },
            {
              name: "Rehan Abad Siddiqui",
              position: "V.D Lead FB2021",
              image: "rehan.jpeg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/_abadrehan?igshid=kynl9e6k5x9v"
                },
                { name: "email", image: "email.png", link: "mailto:siddiquirehanabad@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/rehan-abad-siddiqui-623868176" }
              ]
            },
            {
              name: "Waris Khan",
              position: "Brakes Lead FB2021",
              image: "IMG_20191130_010441.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/waris______khan?igshid=12n9s65qrt0pd"
                },
                { name: "email", image: "email.png", link: "mailto:wariskhan1998@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/waris-khan-a40110134/" }
              ]
            },
            {
              name: "Shubham Jain",
              position: "Cost Lead SUPRA 19",
              image: "shubham.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link: "https://instagram.com/mech_hustle?igshid=1h1fw0zzq35l5"
                },
                { name: "email", image: "email.png", link: "maito:shubham.jain.alig@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/shubham-jain-891726144" }
              ]
            },
            {
              name: "Hina Tomar",
              position: "Electronics Member FB2020",
              image: "IMG_20191125_200003.jpg",
              links: [
                {
                  name: "insta",
                  image: "insta.png",
                  link:
                    "https://instagram.com/hinatomar868?igshid=1szlw7xxvvsrd"
                },
                { name: "email", image: "email.png", link: "mailto:hinatomar868@gmail.com" },
                { name: "linkedin", image: "linkedin.png", link: "https://www.linkedin.com/in/hinatomar22" }
              ]
            }
      ]
    };
  }
};
</script>

<style scoped>
main {
  background-image: url("../assets/images/background/carback.jpg");
  background-size: 100vw 100vh;
  background-attachment: fixed;
  position: relative;
  padding-bottom: 50px;
  padding-top: 1px;
}
main > div {
  border: 5px white ridge;
  margin: 5% 2%;
  margin-top: 8rem;
}
#zfr5 {
  position: relative;
  top: -70px;
}
#top-member {
  margin-top: 0;
  padding-top: 0;
}
.firsttier {
  margin: 30px 0;
  padding: 30px;
  /* border: 2px solid green; */
}
.firsttier > div {
  width: fit-content;
  min-width: 250px;
  max-width: 300px;
  margin: auto;
  transition: transform 300ms;
}
.firsttier > div,
.second-tier > div {
  box-shadow: 0 0 20px 5px rgb(14, 14, 14), inset 0 -1px 0 0 #dadce0;
  border-radius: 12px;
  background: lightgray;
}
.member {
  margin-top: 10px;
  /* padding: 10px; */
}
.member > div {
  margin: 20px 0;
  text-align: center;
}
.member-image img {
  margin-top: 12px;
  width: 60%;
  border-radius: 70% 30% 50% 50% / 70% 70% 30% 30%;
  box-shadow: 0 0 12px 0px rgb(0, 0, 0);
}
.second-tier {
  margin: 30px 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  align-content: space-around;
}
.second-tier > div {
  margin: 50px 15px;
  flex-basis: 40% !important;
  min-width: 230px;
  max-width: 260px;
  transition: transform 300ms;
}
.second-tier > div:hover,
.firsttier > div:hover {
  transform: scale(1.1);
}
.linksofmembers {
  margin: 20px 0;
  display: flex;
  justify-content: space-around;
  background-color: rgb(138, 138, 138);
  margin: 0 0 -30px 0;
  border-bottom-right-radius: 12px;
  border-bottom-left-radius: 12px;
  padding: 12px 0;
}
.linksofmembers div a img:hover {
  transform: scale(1.1);
}
.linksofmembers div {
  padding-bottom: 5px;
  transition: border-bottom 300ms;
}
.linksofmembers div:hover {
  border-bottom: 2px solid #330926;
}
.linksofmembers div a img {
  height: 40px;
  border-radius: 50%;
  transition: transform 400ms;
  /* box-shadow: 0 0 5px 0 black; */
}
.perse-des,
.perse-des-small {
  color: rgb(18, 62, 98);
  font-family: Domile;
}
.perse-des h2,
.perse-des-small h2 {
  padding: 1%;
  font-weight: 700;
  border-bottom: 4px ridge black;
  color: #000;
}
.perse-des h2 {
  font-size: 1.8rem;
}
.perse-des h4 {
  font-size: 1.4rem;
}
.perse-des-small h2 {
  font-size: 1.4rem;
}
.perse-des-small h4 {
  font-size: 1.1rem;
}
.department-heading > div {
  padding: 1% 10%;
  color: white;
  font-weight: 800;
  font-family: Roboto;
  text-shadow: #000 4px 3px 3px;
  /* text-decoration: underline white; */
  margin: auto;
  width: 80%;
  border-radius: 12px;
  background-color: #09332a;
}
.department-heading-box {
  border-bottom: 2px ridge white;
  margin: auto;
  width: fit-content;
}
.department-heading-box h1 {
  text-align: center;
}
#zfr5 {
  margin-top: 30px;
}
#zfr5 > div {
  width: 95%;
  background: linear-gradient(45deg, #1f171c, rgb(87, 40, 40), #1f171c);
}
@media screen and (max-width: 991px) {
  main {
    background-image: url("../assets/images/background/carback.r.jpg");
  }
  #zfr5 {
    top: -60px;
  }
  .department-heading-box h1 {
    font-size: 1.5rem;
  }
  .perse-des h2 {
    font-size: 1.6rem;
  }
  .second-tier {
    margin: 8% 0;
  }
  .firsttier {
    margin: 4% 0;
  }
  .perse-des h4 {
    font-size: 1.2rem;
  }
}
</style>