<template>
  <ion-menu side="start" menu-id="nav" content-id="main">
    <ion-header>
      <ion-toolbar>
        <ion-title>Navigation</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <ion-list>
        <ion-item v-for="n in navs" :key="n.goto" class="nav-item" @click="scrollToEl(n.goto)">
          {{ n.text }}
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-menu>

  <ion-page>
  
    <ion-header :translucent="true">
        <ion-toolbar>
          <ion-buttons slot="start" v-if="screen.width < breakpoint">
            <ion-button @click="openMenu()">
              <ion-icon slot="start" :icon="menu"></ion-icon>
            </ion-button>
          </ion-buttons>

          <ion-title class="title" @click="scrollToTop()">Pandemics' Symposium @ HICSS 2024</ion-title>

          <ion-buttons slot="primary" v-if="screen.width >= breakpoint">
            <template v-for="n in navs" :key="n.goto">
              <ion-button @click="scrollToEl(n.goto)">
                {{ n.text }}
                <ion-icon slot="start" :icon="n.icon"></ion-icon>
              </ion-button>
            </template>
          </ion-buttons>

          <!-- <ion-buttons slot="end">
            <language-switcher></language-switcher>
          </ion-buttons> -->
        </ion-toolbar>
    </ion-header>

    <ion-content id="main" ref="content" :fullpage="true" :scroll-events="true" v-on:ion-scroll="getScrollPos($event.detail.scrollTop)">
      <ion-card id="abstract">
            <!-- <img style="width:100%;" alt="Image of VCC building with the main entrance" :src="require('@/'+t('vccimg')+'.png')" /> -->
            <ion-card-header>
              <ion-card-title>
                Symposium on Novel Data, Analytics, Predictive Intelligence, and Decision-Making for Pandemics and Emerging Diseases
              </ion-card-title>
            </ion-card-header>

            <ion-card-content>
              <h2 style="margin-bottom:20px;font-weight:bold;">Wednesday, January 3rd, 2024 (9 am - 4 pm). Hilton Hawaiian Village Waikiki Beach Resort, Waikiki, Hawaii, USA</h2>
              
              <p>
                The events of the last three years with the spread of the SARS-CoV-2 virus and the outbreak of COVID-19 becoming a global pandemic have had catastrophic effects in many parts of the world and continue to have lasting ripple effects, many of which won’t fully be realized for decades to come. As COVID-19 becomes endemic, it is crucial to identify gaps in research, infrastructure, policy, and communication to better prepare for when, not if, we are faced with these circumstances again.
              </p>

              <p>
                It begins with smarter surveillance. Providing earlier and more accurate detection and prevalence monitoring of emerging infectious diseases (EIDs) and disease/syndrome indicators across all stages of a pandemic is imperative. We can’t see emerging threats if we aren’t looking, and novel, intelligent approaches to the “canary in the coal mine” will afford us the ability to perhaps respond to outbreaks before they occur rather than react to them once they have fully emerged.
              </p>

              <p>
                Better data drives smarter decision-making. Implementing data-driven syndromic and epidemiological models that harness novel AI-enabled methods to monitor, integrate, and correlate sources across a range of scales for pandemic detection and prediction is a must. This requires models that are designed to be nimble, agile, and capable of ingesting important data and information products as they are discovered. Realizing this requires addressing issues of scale, data fusion, and data integrity.
              </p>

              <p>
                A coordinated, transparent, and trustworthy response combats misinformation. Developing intelligent, interactive response planning and monitoring systems that scale these new data sources and analytical methods across the community, state, and national levels that account for diverse population dynamics and disease spread is crucial to communicate in a real-time state to a broad audience of stakeholders. Transparency is a necessary component to engender trust, a critical underpinning to communicating risk.  
              </p>

              <p>
                This symposium will bring together stakeholders working in the area of pandemic preparedness to discuss and provide a better understanding and predictions of where issues like climate change, urbanization, and environmental degradation affect the ecologies of humans and animals and increase disease emergence risk, taking a OneHealth approach. Additionally, this symposium will address the application of these novel surveillance, identification, and data science methods on infectious diseases already of importance in the US and across the world, reducing the overall impact of the inevitable future infectious diseases.
              </p>
            </ion-card-content>
          </ion-card>


          <ion-card id="session1">
            <ion-card-header>
              <ion-card-title>
                Session 1: Novel data sources and data fusion (90 min)
              </ion-card-title>
            </ion-card-header>

            <ion-card-content class="vcc">
              <p>
                During COVID-19, a variety of data sources proved useful to inform the myriad of models being run to predict transmission of the SARS-CoV-2 virus. One such data source that was heavily used was anonymized mobility data provided by entities such as SafeGraph to estimate how mobile people and communities were during the various stages of lock-down. Additionally, social media data was used to gauge acceptance of the non-pharmaceutical interventions and to gauge compliance with vaccinations against the virus. Additionally, accessing wastewater samples for pathogen identification in population samples, analyzing volatile organic compounds (VOC) from the breath samples have also shown to be very promising data streams in developing markers to identify SARS-CoV-2. Significant issues emerge when fusing disparate data over different time scales and spatial scales. It seems clear that the ability to quickly fuse these novel data together to surveil the health of a population will become more prevalent, and strategies for quickly assessing the value, quality and efficacy of a novel data source will be required. 
              </p>

              <ion-grid>
                <ion-row>
                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Velmurugan Thavasi" :src="require('@/vt.jpg')" />

                    <h1 class="name">Velmurugan Thavasi</h1>

                    <ul class="info">
                      <li>Senior Researcher</li>
                      <li>Center for Quantum Research and Technology (CQRT)</li>
                      <li>University of Oklahoma</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Jason Vogel" :src="require('@/jv.jpg')" />

                    <h1 class="name">Jason Vogel</h1>

                    <ul class="info">
                      <li>Professor, Civil Engineering and Environmental Science</li>
                      <li>Director, Oklahoma Water Survey</li>
                      <li>Associate Director, Water Technologies for Emerging Regions (WaTER) Center</li>
                      <li>University of Oklahoma</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Kelly Gaither" :src="require('@/kg.jpg')" />

                    <h1 class="name">Kelly Gaither</h1>

                    <ul class="info">
                      <li>Deputy Director, Senior Research Scientist, Texas Advanced Computing Center</li>
                      <li>Associate Professor, Department of Women's Health, Dell Medical School</li>
                      <li>The University of Texas at Austin</li>
                    </ul>
                  </ion-col>

                </ion-row>
              </ion-grid>
            </ion-card-content>
          </ion-card>

          <h4 style="text-align: center">Morning break</h4>

          <ion-card id="session2">
            <ion-card-header>
              <ion-card-title>
                Session 2: Modeling (90 min)
              </ion-card-title>
            </ion-card-header>

            <ion-card-content class="vcc">
              <p>
                Transmission dynamics modeling was (and continues to be) highly valued by decision makers in the COVID-19 response. Although there are a variety of approaches with a range of skill sets to transmission dynamics modeling, many challenges remain. One challenge is that in many cases, ensemble approaches have not consistently outperformed baseline models. Another challenge is that decision makers continue to see modeling as a black box and tend to be distrustful of them. To address these challenges, multidisciplinary teams need to use better data sources to communicate strengths and limitations from their models, and make them accessible to a wider audience.
              </p>

              <ion-grid>
                <ion-row>
                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Marco Ajelli" :src="require('@/ma.jpg')" />

                    <h1 class="name">Marco Ajelli</h1>

                    <ul class="info">
                      <li>Accociate Professor, Epidemiology and Biostatistics</li>
                      <li>School of Public Health</li>
                      <li>Indiana University</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Charles Nicholson" :src="require('@/cn.jpg')" />

                    <h1 class="name">Charles Nicholson</h1>

                    <ul class="info">
                      <li>Associate Professor</li>
                      <li>Department of Industrial and Systems Engineering</li>
                      <li>Department of Data Science and Analytics</li>
                      <li>University of Oklahoma</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Aaron Wendelboe" :src="require('@/aw.jpg')" />

                    <h1 class="name">Aaron Wendelboe</h1>

                    <ul class="info">
                      <li>Professor, Epidemiology</li>
                      <li>Edward E. and Helen T. Bartlett Chair in Public Health</li>
                      <li>Williams Companies Foundation Presidential Professor</li>
                      <li>Department of Biostatistics and Epidemiology</li>
                      <li>The University of Oklahoma Health Sciences Center</li>
                    </ul>
                  </ion-col>

                </ion-row>
              </ion-grid>
            </ion-card-content>
          </ion-card>

          <h4 style="text-align: center">Lunch break</h4>
          

          <ion-card id="session3">
            <ion-card-header>
              <ion-card-title>
                Session 3: Decision-making (90 min)
              </ion-card-title>
            </ion-card-header>

            <ion-card-content class="vcc">
              <p>
                Decision-making is influenced by the data and the models and how this information is represented to the user through visualizations and user interfaces. Many factors must be considered, especially concerning the use of multiple data sources. One critical aspect is uncertainties which can originate from the data and models. From the human perspective, biases that influence the decision-making process need to be considered. Finally, pandemics are unique in that, frequently, critical information may not be readily available as data to be modeled but must be considered by the user. This requires interactive user interfaces allowing the user to influence the models and their outcome, effectively creating the human-in-the-loop.
              </p>

              <ion-grid>
                <ion-row>
                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Kelly Gaither" :src="require('@/kg.jpg')" />

                    <h1 class="name">Kelly Gaither</h1>

                    <ul class="info">
                      <li>Deputy Director, Senior Research Scientist, Texas Advanced Computing Center</li>
                      <li>Associate Professor, Department of Women's Health, Dell Medical School</li>
                      <li>The University of Texas at Austin</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Katrin Kuhn" :src="require('@/kk.jpg')" />

                    <h1 class="name">Katrin Kuhn</h1>

                    <ul class="info">
                      <li>Assistant Professor</li>
                      <li>Department of Biostatistics and Epidemiology</li>
                      <li>The University of Oklahoma Health Sciences Center</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Suzanne Pierce" :src="require('@/sp.jpg')" />

                    <h1 class="name">Suzanne Pierce</h1>

                    <ul class="info">
                      <li>Research Scientist</li>
                      <li>Intelligent Decision Support Systems</li>
                      <li>Texas Advanced Computing Center</li>
                      <li>The University of Texas at Austin</li>
                    </ul>
                  </ion-col>

                </ion-row>
              </ion-grid>
            </ion-card-content>
          </ion-card>

          <h4 style="text-align: center">Afternoon break</h4>

          <ion-card id="session4">
            <ion-card-header>
              <ion-card-title>
                Session 4: Infrastructure, scaling and deployment (90 min)
              </ion-card-title>
            </ion-card-header>

            <ion-card-content class="vcc">
              <p>
                Syndromic surveillance traditionally relies on continuous monitoring and analysis of large, existing, electronic records. These data sources can come from clinical or public health sources, but typically act in isolation. Unfortunately, syndromic surveillance has been plagued by its reality of aiming to detect rare (i.e., low prevalent) events that have a corresponding poor positive predictive value. Consequently, false alarms are generated from these systems. To elevate syndromic surveillance methods, we need better tools to automatically rule-out false alarms in order to focus on true events. One path forward is to integrate information from multiple data sources that will provide more detail about true events under detection.
              </p>

              <ion-grid>
                <ion-row>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="David Ebert" :src="require('@/de.jpg')" />

                    <h1 class="name">David Ebert</h1>

                    <ul class="info">
                      <li>Gallogly Chair Professor of ECE and CS</li>
                      <li>Associate Vice President of Research and Partnerships</li>
                      <li>Director, Data Institute for Societal Challenges (DISC)</li>
                      <li>University of Oklahoma</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Ann Chou" :src="require('@/ac.jpg')" />

                    <h1 class="name">Ann Chou</h1>

                    <ul class="info">
                      <li>Professor</li>
                      <li>Department of Family and Preventive Medicine</li>
                      <li>The University of Oklahoma Health Sciences Center</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Maytal Dahan" :src="require('@/md.jpg')" />

                    <h1 class="name">Maytal Dahan</h1>

                    <ul class="info">
                      <li>Director</li>
                      <li>Advanced Computing Interfaces</li>
                      <li>Texas Advanced Computing Center (TACC)</li>
                      <li>University of Texas</li>
                    </ul>
                  </ion-col>
                  

                </ion-row>
              </ion-grid>
            </ion-card-content>
          </ion-card>

          <ion-card id="cochairs">
            <ion-card-header>
              <ion-card-title>
                SWT leaders
              </ion-card-title>
            </ion-card-header>

            <ion-card-content class="vcc">
              <ion-grid>
                <ion-row>
                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="David Ebert" :src="require('@/de.jpg')" />

                    <h1 class="name">David Ebert</h1>

                    <ul class="info">
                      <li>Gallogly Chair Professor of ECE and CS</li>
                      <li>Associate Vice President of Research and Partnerships</li>
                      <li>Director, Data Institute for Societal Challenges (DISC)</li>
                      <li>University of Oklahoma</li>
                    </ul>
                  </ion-col>

                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Kelly Gaither" :src="require('@/kg.jpg')" />

                    <h1 class="name">Kelly Gaither</h1>

                    <ul class="info">
                      <li>Deputy Director, Senior Research Scientist, Texas Advanced Computing Center</li>
                      <li>Associate Professor, Department of Women's Health, Dell Medical School</li>
                      <li>The University of Texas at Austin</li>
                    </ul>
                  </ion-col>


                  <ion-col size="12" size-sm class="speaker">
                    <img class="img" alt="Aaron Wendelboe" :src="require('@/aw.jpg')" />

                    <h1 class="name">Aaron Wendelboe</h1>

                    <ul class="info">
                      <li>Professor, Epidemiology</li>
                      <li>Edward E. and Helen T. Bartlett Chair in Public Health</li>
                      <li>Williams Companies Foundation Presidential Professor</li>
                      <li>Department of Biostatistics and Epidemiology</li>
                      <li>The University of Oklahoma Health Sciences Center</li>
                    </ul>
                  </ion-col>

                </ion-row>
              </ion-grid>
            </ion-card-content>
          </ion-card>
    </ion-content>


  <div class="back-to-top-btn" v-if="showScrollTop" @click="scrollToTop()">
    <ion-icon :icon="chevronUp"></ion-icon>
  </div>
    
  </ion-page>
</template>

<script lang="ts">
// import LanguageSwitcher from '@/components/LanguageSwitcher.vue';
import { IonGrid, IonRow, IonCol, IonButton, IonButtons, IonCard, IonCardContent, IonCardHeader, IonCardTitle, IonContent, IonHeader, IonIcon, IonItem, IonList, IonMenu, IonPage, IonTitle, IonToolbar, menuController } from '@ionic/vue';
import { chevronUp, airplane, train, bus, boat, location, car, bed, help, menu, call } from 'ionicons/icons';
import { defineComponent, ref } from 'vue';
import { useI18n } from 'vue-i18n';
import { useScreen } from 'vue-screen'

export default defineComponent({
  name: 'HomePage',
  components: {
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonCard,
    IonCardContent, IonCardHeader, IonCardTitle, IonIcon,
    IonButton,
    IonContent,
    IonGrid,
    IonRow,
    IonCol,
    IonButtons,
    IonItem,
    IonMenu,
    IonList,
    // LanguageSwitcher
  },
  setup() {
    const { t } = useI18n();
    const screen = useScreen();
    const breakpoint = 1400;

    const content = ref();
    const scrollToEl = (id: string) => {
      const titleELe = document.getElementById(id);
      if (!titleELe) {
        return;
      }
      menuController.close('nav');
      content.value.$el.scrollToPoint(0, titleELe.offsetTop, 1000);
    };

    const scrollToTop = () => {
      content.value.$el.scrollToTop(1000);
    }

    const showScrollTop = ref(false);

    const getScrollPos = (pos: number) => {
      showScrollTop.value = pos > 100;
    };

    menuController.enable(true, 'nav');
    const openMenu = () => {
      menuController.open('nav');
    }

    const navs = ref([
      {
        text: 'Info',
        goto: 'abstract'
      },
      {
        text: 'Session 1',
        goto: 'session1'
      },
      {
        text: 'Session 2',
        goto: 'session2'
      },
      {
        text: 'Session 3',
        goto: 'session3'
      },
      {
        text: 'Session 4',
        goto: 'session4'
      },
      {
        text: 'SWT Leaders',
        goto: 'cochairs'
      }
    ]);

    return {
      t,
      airplane,
      train,
      bus,
      boat,
      location,
      car,
      bed,
      content,
      scrollToEl,
      scrollToTop,
      chevronUp,
      getScrollPos,
      showScrollTop,
      help,
      openMenu,
      menu,
      navs,
      screen,
      breakpoint,
      call
    }
  }
});
</script>

<style scoped>
.vcc h2, .vcc h3 {
  margin-top: 15px;
}

.vcc h2:first-child  {
  margin-top: auto;
}

.back-to-top-btn {
  cursor: pointer;
    background: rgba(158, 158, 158, 0.5);
    position: fixed;
    border-radius: 50%;
    width: 50px;
    height: 50px;
    color: #000;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 1px 2px 0 rgba(0,0,0,.1);
    
    right: 10px;
    transform: translateX(-50%);
    bottom: 35px;
    z-index: 999;
}

.nav-item {
  cursor:pointer;
}

.nav-item:hover {
  --ion-background-color: #d6d6d6 !important;
}

.speaker {

}

.speaker .img {
  border-radius: 50%;
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}

.speaker .name {
  text-align: center;
  font-size: 20px
}

.speaker .info {
  list-style-type: none;
  padding-left: 0px;
}

.speaker .info li {
  margin-top: 5px;
  margin-bottom: 5px;
}
</style>
