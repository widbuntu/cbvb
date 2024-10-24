<template>
    <v-container fluid>
        <v-row>

            <!-- Main Content Area -->
            <v-col cols="12" md="8">

                <!-- Ad Banner -->
                <v-row justify="center">
                    <v-col cols="12" class="text-center">
                        <v-hover v-slot="{ isHovering, props }">
                            <a href="https://centerpointsecurities.com/?promo=cbvb" target="_blank" v-bind="props">
                                <v-card :elevation="isHovering ? 4 : 2" :class="{ 'scale-card': isHovering }"
                                    max-width="1200">
                                    <v-img
                                        src="https://www.collegebeachvb.com/_next/image?url=%2Fimages%2Fpartners%2Fcp_logo.jpg&w=1920&q=75"
                                        alt="Baden" />
                                </v-card>
                            </a>
                        </v-hover>
                    </v-col>
                </v-row>

                <!-- Headlines Section -->
                <v-row class="mt-5">
                    <v-col cols="12">
                        <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
                            <h2 class="text-h4 font-weight-bold">HEADLINES</h2>
                            <v-sheet class="inner-box pa-4" color="#e1edf5" rounded="lg">
                                <v-img
                                    src="https://cloud-cube-us2.s3.amazonaws.com/fd9w2bq284gw/public/usc-natl2024-05-19.jpeg"
                                    alt="USC wins the 2024 NCAA National Championships" aspect-ratio="16/9" />
                                <v-card-title class="text-h5">
                                    <a href="https://usctrojans.com/news/2024/5/5/womens-beach-volleyball-usc-beach-volleyball-four-peats.aspx"
                                        target="_blank" class="text-decoration-none">
                                        USC wins the 2024 NCAA National Championships
                                    </a>
                                </v-card-title>
                                <v-card-text>
                                    Sunday, May 19, 2024, Read full USC press release below. <v-btn color="primary"
                                        href="https://usctrojans.com/news/2024/5/5/womens-beach-volleyball-usc-beach-volleyball-four-peats.aspx"
                                        target="_blank" variant="text">Read More</v-btn>

                                </v-card-text>
                            </v-sheet>
                        </v-sheet>
                    </v-col>
                </v-row>

                <!-- Small Headlines -->
                <v-row class="mt-5">
                    <v-col cols="6">
                        <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
                            <v-sheet class="inner-box pa-4" color="#e1edf5" rounded="lg">
                                <v-img
                                    src="https://www.collegebeachvb.com/_next/image?url=https%3A%2F%2Fcloud-cube-us2.s3.amazonaws.com%2Ffd9w2bq284gw%2Fpublic%2Fusc12024-04-28.jpeg&w=3840&q=75"
                                    alt="USC wins the 2024 NCAA National Championships" aspect-ratio="16/9" />
                                <v-card-title class="text-h5">
                                    <a href="https://usctrojans.com/news/2024/5/5/womens-beach-volleyball-usc-beach-volleyball-four-peats.aspx"
                                        target="_blank" class="text-decoration-none">
                                        The NCAA Bracket was released today. Click on the link below for all your
                                        information from Gulf Shores.
                                    </a>
                                </v-card-title>
                                <v-card-text>
                                    Sunday, April 28, 2024, Play will begin on May 3rd... <v-btn color="primary"
                                        href="https://usctrojans.com/news/2024/5/5/womens-beach-volleyball-usc-beach-volleyball-four-peats.aspx"
                                        target="_blank" variant="text">Read More</v-btn>

                                </v-card-text>
                            </v-sheet>
                        </v-sheet>
                    </v-col>
                    <v-col cols="6">
                        <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
                            <v-sheet class="inner-box pa-4" color="#e1edf5" rounded="lg">
                                <v-img
                                    src="https://www.collegebeachvb.com/_next/image?url=https%3A%2F%2Fcloud-cube-us2.s3.amazonaws.com%2Ffd9w2bq284gw%2Fpublic%2Fuclasenior2024-04-09.jpeg&w=3840&q=75"
                                    alt="USC wins the 2024 NCAA National Championships" aspect-ratio="16/9" />
                                <v-card-title class="text-h5">
                                    <a href="https://usctrojans.com/news/2024/5/5/womens-beach-volleyball-usc-beach-volleyball-four-peats.aspx"
                                        target="_blank" class="text-decoration-none">
                                        Wednesday, April 10, 2024, Long Beach State defeated Cal...
                                    </a>
                                </v-card-title>
                                <v-card-text>
                                    Wednesday, April 10, 2024, Long Beach State defeated Cal... <v-btn color="primary"
                                        href="https://usctrojans.com/news/2024/5/5/womens-beach-volleyball-usc-beach-volleyball-four-peats.aspx"
                                        target="_blank" variant="text">Read More</v-btn>

                                </v-card-text>
                            </v-sheet>
                        </v-sheet>
                    </v-col>
                </v-row>

                <!-- Latest -->
                <!-- Scores Section -->
                <v-row class="mt-5">
                    <v-col cols="12">
                        <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
                            <h2 class="text-h4 font-weight-bold mb-4">LATEST SCORES</h2>
                            <v-table hover density="comfortable" class="scores-table rounded-lg">
                                <thead>
                                    <tr>
                                        <th v-for="header in latestHeaders" :key="header.value"
                                            class="text-left primary">
                                            {{ header.text }}
                                        </th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <template v-for="(item, index) in latestItems" :key="index">
                                        <!-- Main score row -->
                                        <tr @mouseenter="selectedMatch = index" @mouseleave="selectedMatch = null"
                                            :class="{ 'highlighted-row': selectedMatch === index }">
                                            <td v-for="header in latestHeaders" :key="header.value" class="text-body-1">
                                                {{ item[header.value] }}
                                            </td>
                                        </tr>

                                        <!-- Nested details row -->
                                        <tr v-if="selectedMatch === index">
                                            <td :colspan="latestHeaders.length" class="pa-0">
                                                <v-expand-transition>
                                                    <div v-show="selectedMatch === index"
                                                        class="nested-details bg-grey-lighten-5">
                                                        <v-table density="comfortable" class="nested-table mx-2 my-2">
                                                            <thead>
                                                                <tr>
                                                                    <th v-for="header in recentScoreHeaders"
                                                                        :key="header.value" class="text-left secondary">
                                                                        {{ header.text }}
                                                                    </th>
                                                                </tr>
                                                            </thead>
                                                    <tbody>
                                                        <tr v-for="(score, scoreIndex) in recentScores[index]" :key="scoreIndex"
                                                            class="nested-row">
                                                            <td>{{ score.position }}</td>
                                                            <td>{{ score.teamOne }}</td>
                                                            <td>{{ score.teamTwo }}</td>
                                                            <td>{{ score.winner }}</td>
                                                            <td>{{ score.score }}</td>
                                                        </tr>
                                                    </tbody>
                                                        </v-table>
                                                    </div>
                                                </v-expand-transition>
                                            </td>
                                        </tr>
                                    </template>
                                </tbody>
                            </v-table>
                        </v-sheet>
                    </v-col>
                </v-row>

                <!-- Baden Ad -->
                <v-row>
                    <v-col cols="12" class="text-center">
                        <v-hover v-slot="{ isHovering, props }">
                            <a href="https://centerpointsecurities.com/?promo=cbvb" target="_blank" v-bind="props">
                                <v-card :elevation="isHovering ? 4 : 2" :class="{ 'scale-card': isHovering }" max-width="800">
                                    <v-img
                                        src="https://www.collegebeachvb.com//_next/image?url=%2Fimages%2Fpartners%2Fbaden.jpeg&w=750&q=75"
                                        alt="Baden" />
                                </v-card>
                            </a>
                        </v-hover>
                    </v-col>
                </v-row>

        </v-col>

<!-- Sidebar -->
<v-col cols="12" md="4">

    <!-- Pair of the Week Card -->
    <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
        <h2>AVCA/CollegeBeachVb Pair of the Week</h2>
        <!-- Inner colored box -->
        <v-sheet class="inner-box pa-4" color="#e1edf5" rounded="lg">
            <p>
                Maddi Kriz and Madison White of USC went 3-0 this past weekend and
                had a big three set win at the #2 position to help the Trojans win the NCAA
                Championship.
            </p>
        </v-sheet>
    </v-sheet>

    <!-- Team Rankings Card -->
    <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
        <v-card-title class="d-flex justify-space-between align-center">
            <h2>Team Rankings</h2>
            <v-btn variant="text" href="https://www.truvolley.com/ncaa" target="_blank">
                About TruVolley
            </v-btn>
        </v-card-title>
        <v-table density="compact" class="rankings-table">
            <thead>
                <tr>
                    <th v-for="header in headers" :key="header.value" class="text-left">
                        {{ header.text }}
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in items" :key="item.rank">
                    <td v-for="header in headers" :key="header.value">
                        {{ item[header.value] }}
                    </td>
                </tr>
                <v-btn color="primary" href="/" target="_blank" variant="text">Get More...</v-btn>
            </tbody>
        </v-table>
    </v-sheet>

    <!-- Indiv Rankings Card -->
    <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
        <v-card-title class="d-flex justify-space-between align-center">
            <h2>Individual Rankings</h2>
        </v-card-title>
        <v-table density="compact" class="rankings-table">
            <thead>
                <tr>
                    <th v-for="header in indivHeaders" :key="header.value" class="text-left">
                        {{ header.text }}
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in indivItems" :key="item.rank">
                    <td v-for="header in indivHeaders" :key="header.value">
                        {{ item[header.value] }}
                    </td>
                </tr>
                <v-btn color="primary" href="/" target="_blank" variant="text">Get More...</v-btn>
            </tbody>
        </v-table>
    </v-sheet>

    <!-- Top NCAA Pairs -->
    <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
        <v-card-title class="d-flex justify-space-between align-center">
            <h2>Top NCAA Pairs/Players</h2>
        </v-card-title>
        <v-table density="compact" class="rankings-table">
            <thead>
                <tr>
                    <th v-for="header in topPairsHeaders" :key="header.value" class="text-left">
                        {{ header.text }}
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in topPairsItems" :key="item.rank">
                    <td v-for="header in topPairsHeaders" :key="header.value">
                        {{ item[header.value] }}
                    </td>
                </tr>
                <v-btn color="primary" href="/" target="_blank" variant="text">Get More...</v-btn>
            </tbody>
        </v-table>
    </v-sheet>

    <!-- Top JUCO Pairs -->
    <v-sheet class="outer-box pa-4 mb-4" elevation="1" rounded="lg">
        <v-card-title class="d-flex justify-space-between align-center">
            <h2>Top JUCO Pairs/Players</h2>
        </v-card-title>
        <v-table density="compact" class="rankings-table">
            <thead>
                <tr>
                    <th v-for="header in topPairsHeaders" :key="header.value" class="text-left">
                        {{ header.text }}
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in topJucoItems" :key="item.rank">
                    <td v-for="header in topPairsHeaders" :key="header.value">
                        {{ item[header.value] }}
                    </td>
                </tr>
                <v-btn color="primary" href="/" target="_blank" variant="text">Get More...</v-btn>
            </tbody>
        </v-table>
    </v-sheet>

</v-col>

<!-- Latest table -->


</v-row>


<br>
<h2>Partners</h2>

<v-row>
    <v-col cols="3" class="text-center">
        <v-hover v-slot="{ isHovering, props }">
            <a href="https://www.oakley.com/en-us" target="_blank" v-bind="props">
                <v-card :elevation="isHovering ? 3 : 2" :class="{ 'scale-card': isHovering }" max-width="400">
                    <v-img
                        src="https://www.collegebeachvb.com/_next/image?url=%2Fimages%2Fpartners%2Foakley.jpg&w=384&q=75"
                        alt="Oakley" />
                </v-card>
            </a>
        </v-hover>
    </v-col>

    <v-col cols="3" class="text-center">
        <v-hover v-slot="{ isHovering, props }">
            <a href="https://www.rawelementsusa.com/" target="_blank" v-bind="props">
                <v-card :elevation="isHovering ? 4 : 2" :class="{ 'scale-card': isHovering }" max-width="200">
                    <v-img
                        src="https://www.collegebeachvb.com/_next/image?url=%2Fimages%2Fpartners%2Fraw-elements.png&w=256&q=75"
                        alt="Raw Elements" />
                    <div class="mt-2">
                        Use Promocode CBVB10OFF to receive 10% off all Raw Elements Purchases
                    </div>
                </v-card>
            </a>
        </v-hover>
    </v-col>
</v-row>


</v-container>
</template>

<script setup>

import { ref } from 'vue'

const recentScores = [
  [
    { 
        position: '2',
        teamOne: 'USC (Maddi Kriz/Madison White)',
        teamTwo: 'UCLA (Devon Newberry/Peri Brennan)',
        winner: 'USC',
        score: '14-21, 21-19, 15-13'
    },
    {
        position: '3',
        teamOne: 'USC (Audrey Nourse/Nicole Nourse)',
        teamTwo: 'UCLA (Kenzie Brower/Jessica Smith)',
        winner: 'USC',
        score: '22-20, 15-21, 15-11'
    },
    {
        position: '4',
        teamOne: 'USC (Ashley Pater/Grace Seits)',
        teamTwo: 'UCLA (Jaden Whitemarse/Tessa Van Winkle)',
        winner: 'USC',
        score: '24-26, 25-23, 15-8'
    }
  ],
  [
    {
        position: '1',
        teamOne: 'UCLA (Lexy Denaburg/Maggie Boyd)',
        teamTwo: 'LSU (Ellie Shank/GabiBailey)', 
        winner: 'UCLA', 
        score:  '21-19, 21-14'
    },
    {
        position: '2',
        teamOne: 'UCLA (Devon Newberry/Peri Brennan)',
        teamTwo: 'LSU (Parker Bracken/Reilly Allred)', 
        winner: 'LSU', 
        score:  '23-21, 21-18'
    },
    {
        position: '3',
        teamOne: 'UCLA (Kenzie Brower/Jessica Smith)',
        teamTwo: 'LSU (Aubrey O`Gorman/Ella Larkin)', 
        winner: 'UCLA', 
        score:  '21-19, 21-19'
    },
    {
        position: '4',
        teamOne: 'UCLA (Jaden Whitemarsh/Tessa Van Winkle)',
        teamTwo: 'LSU (Amber Haynes/Skylar Martin)', 
        winner: 'UCLA', 
        score:  '21-9, 21-11'
    },
  ],
]

// Toggle the visibility of the nested table for each item
const toggleExpanded = (index) => {
  latestItems.value[index].expanded = !latestItems.value[index].expanded
}

const selectedMatch = ref(null)
const recentScoreHeaders = [
    { text: 'Position', value: 'position' },
    { text: 'Team1', value: 'usc' },
    { text: 'Team2', value: 'ucla' },
    { text: 'Winner', value: 'winner' },
    { text: 'Score', value: 'score' }
]

const latestHeaders = [
    { text: 'Date', value: 'date' },
    { text: 'School', value: 'school' },
    { text: 'Score', value: 'score' },
]

const latestItems = ref([
    { date: '05/05/2024', school: "USC vs UCLA", score: "3-0" },
    { date: '05/04/2024', school: "UCLA vs LSU", score: "3-1" },
    { date: '05/04/2024', school: "USC vs Cal Poly SLO", score: "3-0" },
    { date: '05/04/2024', school: "LSU vs Stanford", score: "3-2" },
])

const topJucoItems = ref([
    { rank: 1, college: 'Palm Beach State College', pair: 'Anna Cruz/Zuzanna Michalska', results: "14-0" },
    { rank: 2, college: 'Richard Blland College of William & Mary', pair: 'Sarah Heath/Alexis Scipione', results: "28-3" },
    { rank: 3, college: 'Wake Technical CC', pair: 'Brooke Geiger/Gabrielle Carter', results: "35-4" },
    { rank: 4, college: 'Spartanburg Methodist College', pair: 'Kendall Meinders/Hana Vucinic', results: "33-7" }
])

const topPairsHeaders = [
    { text: 'Rank', value: 'rank' },
    { text: 'Pair', value: 'pair' },
    { text: 'College', value: 'college' },
    { text: 'Results', value: 'results' },
]

const topPairsItems = ref([
    { rank: 1, college: 'Colroado Mesa', pair: 'Hahni Johnson /Amanda Ollinger', results: "14-0" },
    { rank: 2, college: 'FIU', pair: 'Giada Bianchi/Reka Orsi Toth', results: "28-3" },
    { rank: 3, college: 'USC', pair: 'Megan Kraft/Delaynie Maple', results: "35-4" },
    { rank: 4, college: 'UCLA', pair: 'Hailey Hamlett/Anhelina Khmil', results: "33-7" }
])

const indivHeaders = [
    { text: 'Rank', value: 'rank' },
    { text: 'Player', value: 'player' },
    { text: 'College', value: 'college' },
    { text: 'Rating', value: 'rating' },
]

const indivItems = ref([
    { rank: 1, college: 'Jon', player: 'Super guy', rating: "Diamond" },
    { rank: 1, college: 'Brian', player: 'Fun guy', rating: "Diamond" },
    { rank: 1, college: 'Kevin', player: 'First guy', rating: "Diamond" },
    { rank: 1, college: 'Chris', player: 'Dope guy', rating: "Diamond" }
])

const headers = [
    { text: 'Rank', value: 'rank' },
    { text: 'College', value: 'college' },
    { text: '1s', value: 'ones' },
    { text: '2s', value: 'twos' },
    { text: '3s', value: 'threes' },
    { text: '4s', value: 'fours' },
    { text: '5s', value: 'fives' }
]

const items = ref([
    { rank: 1, college: 'USC', ones: 1, twos: 3, threes: 1, fours: 1, fives: 4 },
    { rank: 2, college: 'UCLA', ones: 2, twos: 1, threes: 2, fours: 3, fives: 1 },
    { rank: 3, college: 'FSU', ones: 5, twos: 6, threes: 3, fours: 7, fives: 5 }
])

</script>


<style scoped>
.rankings-table {
  width: 100%;
  border-collapse: collapse;
}

.rankings-table thead tr {
  background-color: #2780ba;
  color: white;
}

.rankings-table tbody tr {
  background-color: #e1edf5;
  color: #044062;
  cursor: pointer;
}

.nested-details {
  background-color: #f9f9f9;
}

.nested-table {
  width: 100%;
  border: 1px solid #ddd;
}

.nested-table thead tr {
  background-color: #2780ba;
  color: white;
}

.nested-table td, .nested-table th {
  padding: 8px;
  text-align: left;
}

.nested-details {
  border-top: 1px solid rgba(var(--v-border-color), var(--v-border-opacity));
}

tr {
  transition: background-color 0.2s ease;
}

.nested-table-container {
  overflow: hidden;
  transition: max-height 0.3s ease-out;
  background-color: white;
}

.nested-table-container.show {
  max-height: 500px;
  transition: max-height 0.5s ease-in;
}
</style>