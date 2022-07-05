<template>
  <div class="animations">
    <ul>
      <li v-for="(video, key) in videos" :key="key" class="video">
      <iframe width="560" height="315" :src="video.embed" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        <a class="video__url" :href="video.url" target="_blank">{{ video.name }}</a>
        <div class="roles">
          <p v-for="(tag, key) in video.tags" :key="key">{{ tag }}</p>        
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Animation',
  data() {
    return {
      videos: [{
        'name': 'Leave the Elephant Behind | Mobile Assistant',
        'embed': 'https://www.youtube.com/embed/f4g94OlEXxo',
        'url': 'https://www.youtube.com/watch?v=f4g94OlEXxo',
        'tags': ['Animation', 'Sound Effects']
      },{
        'name': 'Elephant in the Room | Mobile Assistant | Mobile Assistant',
        'url': 'https://www.youtube.com/watch?v=Aapd8ytYS2o',
        'embed': 'https://www.youtube.com/embed/Aapd8ytYS2o',
        'tags': ['Animation', 'Sound Effects']
      },{
        'name': 'Building Regulation for Resilience Video | World Bank',
        'embed': 'https://www.youtube.com/embed/XMVLEnjzoAI',
        'url': '',
        'tags': ['Character Animation']
      }]
    }
  }
}
</script>
<style lang="scss">
  iframe {
    margin-bottom: 15px;
  }
  .video {
    max-width: 600px;
    margin: 0 auto;
    margin-bottom: 60px;

    &:last-child {
      margin-bottom: 0;
    }

    &__url {  
      display: block;
    }
  }
  .roles {
    display: flex;
    flex-wrap: nowrap;
    font-size: 12px;

    p {
      position: relative;
      margin-top: 0;
      margin-right: 15px;  

      &:after {
        content: '-';
        position: absolute;
        top: 50%;
        right: -10px;
        opacity: .6;
        transform: translateY(-50%);
      }  
      &:last-child {
        margin-right: 0;

        &:after {
          content: none;
        }
      }
    }
  }
</style>
