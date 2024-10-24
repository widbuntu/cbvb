<template>
  <v-layout>
    <v-main class="pa-0">
      <div class="layoutIndex_top">
        <div class="top-section">
          <!-- Background Image with opacity -->
          <div class="background-wrapper">
            <v-img
              class="banner-index"
              src="https://www.collegebeachvb.com/_next/image?url=%2Fimages%2Fbanner-index.jpg&w=3840&q=75"
              height="32.5vw"
              width="100%"
              cover
            />
          </div>

          <!-- Logo Container, separate from the background image -->
          <div class="logo-container">
            <!-- CBVB Logo - Top Left -->
            <a href="/" class="cbvb-logo">
              <v-img
                src="https://www.collegebeachvb.com/_next/image?url=%2Fimages%2Fcbvb.png&w=640&q=75"
                width="293"
                height="112"
                contain
              />
            </a>

            <!-- AVCA Logo - Bottom Right -->
            <a href="https://www.avca.org/" class="avca-logo" target="_blank">
              <v-img
                src="https://www.collegebeachvb.com/_next/image?url=%2Fimages%2Favca-logo.png&w=384&q=75"
                width="168"
                height="51"
                contain
              />
            </a>
          </div>
        </div>
      </div>
    </v-main>
  </v-layout>
</template>

<style scoped>
.top-section {
  position: relative;
  width: 100%;
}

.background-wrapper {
  position: relative;
}

.banner-index {
  opacity: 0.5; /* Apply opacity only to the background image */
}

/* Logo container to separate logos from the background */
.logo-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-between;
  padding: 24px;
  pointer-events: none;
}

/* CBVB Logo - Positioned at the top left */
.cbvb-logo {
  position: absolute;
  top: 24px;
  left: 24px;
  z-index: 1;
  pointer-events: auto; 
}

/* AVCA Logo - Positioned at the bottom right */
.avca-logo {
  position: absolute;
  bottom: 24px;
  right: 24px;
  z-index: 1;
  pointer-events: auto; 
}

@media (max-width: 600px) {
  /* Adjust for smaller screens */
  .cbvb-logo {
    top: 16px;
    left: 16px;
  }

  .avca-logo {
    bottom: 16px;
    right: 16px;
  }
}
</style>
