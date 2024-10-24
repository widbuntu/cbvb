<template>
  <div class="layout-banner">
    <v-carousel height="100" :continuous="false" show-arrows :cycle="false">
      <template v-slot:prev="{ props }">
        <v-btn color="info" variant="elevated" @click="props.onClick" class="carousel-button" style="opacity: 0.7;">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
            class="bi bi-arrow-bar-left" viewBox="0 0 16 16">
            <path fill-rule="evenodd"
              d="M12.5 15a.5.5 0 0 1-.5-.5v-13a.5.5 0 0 1 1 0v13a.5.5 0 0 1-.5.5M10 8a.5.5 0 0 1-.5.5H3.707l2.147 2.146a.5.5 0 0 1-.708.708l-3-3a.5.5 0 0 1 0-.708l3-3a.5.5 0 1 1 .708.708L3.707 7.5H9.5a.5.5 0 0 1 .5.5" />
          </svg>
        </v-btn>
      </template>
      <template v-slot:next="{ props }">
        <v-btn color="info" variant="elevated" @click="props.onClick" class="carousel-button" style="opacity: 0.7;">
          <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
            class="bi bi-arrow-bar-right" viewBox="0 0 16 16">
            <path fill-rule="evenodd"
              d="M6 8a.5.5 0 0 0 .5.5h5.793l-2.147 2.146a.5.5 0 0 0 .708.708l3-3a.5.5 0 0 0 0-.708l-3-3a.5.5 0 0 0-.708.708L12.293 7.5H6.5A.5.5 0 0 0 6 8m-2.5 7a.5.5 0 0 1-.5-.5v-13a.5.5 0 0 1 1 0v13a.5.5 0 0 1-.5.5" />
          </svg>
        </v-btn>
      </template>
      <v-carousel-item v-for="(group, index) in groupedScores" :key="index" class="carousel-cell">
        <div class="score-group">
          <div v-for="(score, scoreIndex) in group" :key="scoreIndex" class="score-item">
            <a :href="`/scores/competition/${score.id}`" class="score-link">
              <table class="score-table">
                <tbody>
                  <tr>
                    <td colspan="3" class="date-time">{{ score.date }}</td>
                  </tr>
                  <tr>
                    <td>
                      <img :src="score.team1Logo" height="18" :alt="score.team1" />
                    </td>
                    <td style="width: 50%" class="win">{{ score.team1 }}</td>
                    <td class="win">{{ score.team1Score }}</td>
                  </tr>
                  <tr>
                    <td>
                      <img :src="score.team2Logo" height="18" :alt="score.team2" />
                    </td>
                    <td class="loss">{{ score.team2 }}</td>
                    <td class="loss">{{ score.team2Score }}</td>
                  </tr>
                </tbody>
              </table>
            </a>
          </div>
        </div>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>

<script setup>
const scoreData = [
  {
    id: '9203',
    date: "05/03/2024",
    team1: "UCLA",
    team1Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//136.gif",
    team1Score: 3,
    team2: "Texas A&M Corpus Christi",
    team2Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//16.gif",
    team2Score: 0,
  },
  {
    id: '9203',
    date: "05/03/2024",
    team1: "UCLA",
    team1Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//136.gif",
    team1Score: 3,
    team2: "Texas A&M Corpus Christi",
    team2Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//16.gif",
    team2Score: 0,
  },
  {
    id: '9203',
    date: "05/03/2024",
    team1: "UCLA",
    team1Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//136.gif",
    team1Score: 3,
    team2: "Texas A&M Corpus Christi",
    team2Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//16.gif",
    team2Score: 0,
  },
  {
    id: '9203',
    date: "05/03/2024",
    team1: "UCLA",
    team1Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//136.gif",
    team1Score: 3,
    team2: "Texas A&M Corpus Christi",
    team2Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//16.gif",
    team2Score: 0,
  },
  {
    id: '9203',
    date: "05/03/2024",
    team1: "UCLA",
    team1Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//136.gif",
    team1Score: 3,
    team2: "Texas A&M Corpus Christi",
    team2Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//16.gif",
    team2Score: 0,
  },
  {
    id: '9203',
    date: "05/03/2024",
    team1: "UCLA",
    team1Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//136.gif",
    team1Score: 3,
    team2: "Texas A&M Corpus Christi",
    team2Logo: "https://web2.ncaa.org/ncaa_style/img/All_Logos/sm//16.gif",
    team2Score: 0,
  },

];

// Grouping scores into batches of 5
const groupedScores = [];
for (let i = 0; i < scoreData.length; i += 5) {
  groupedScores.push(scoreData.slice(i, i + 5));
}
</script>

<style scoped>
.layout-banner {
  width: 100%;
  background-color: white;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.carousel-cell {
  width: 100%;
  height: 80px;
  display: flex;
  justify-content: center;
}

.score-group {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
}

.score-item {
  width: 20%;
  display: flex;
}

.score-link {
  padding: 0 16px;
}

.score-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 14px;
}

.date-time {
  text-align: center;
  font-weight: bold;
  color: #666;
  padding-bottom: 4px;
}

.win {
  font-weight: bold;
  color: #000;
  text-align: left;
  text-decoration: none;
  padding: 2px 8px;
}

.loss {
  color: #666;
  text-align: left;
  padding: 2px 8px;
}

:deep(.v-carousel__controls) {
  display: none;
}


:deep(.v-window-item) {
  height: 100%;
}
</style>
