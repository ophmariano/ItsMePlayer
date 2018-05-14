<template>
  <div class="video-player">
    <div class="video-container">
      <iframe width="640" height="360" :src="this.activeVideo.youtubeURL" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
      <h3>{{this.activeVideo.title}}</h3>
      <div class="row">
        <p>{{this.activeVideo.views}} views</p>
        <p>{{this.activeVideo.likes}} <button @click="addLike()">Like</button></p>
      </div>
    </div>
    <div class="video-list">
      <div @click="chooseVideo(video)" :key="video.id" v-for="video in videos" class="thumbnail">
        <div class="thumbnail-img">
          <img :src="video.thumbnail" />
        </div>
        <div class="thumbnail-info">
          <h3>{{video.title}}</h3>
          <p>{{video.creator}}</p>
          <p>{{video.likes}} Likes</p>
          <p class="thumbnail-views">{{video.views}} Views </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
let videos = [
  {
    id: 1,
    title: 'God of War Part 1',
    thumbnail:
      'https://i.ytimg.com/vi/YbLIpYpcalk/maxresdefault.jpg',
    youtubeURL: 'https://www.youtube.com/embed/Qq9F0IM5X2w',
    creator: 'Its Me',
    likes: 0,
    views: 1
  },
  {
    id: 2,
    title: 'God of War Part 2',
    thumbnail:
      'https://i.ytimg.com/vi/zXCfNj8tLmE/maxresdefault.jpg',
    youtubeURL: 'https://www.youtube.com/embed/JykUSz5Ye2s',
    creator: 'Its Me',
    likes: 0,
    views: 0
  },
  {
    id: 3,
    title: 'God of War Part 3',
    thumbnail:
      'https://i.ytimg.com/vi/3DJX0r-MYxI/maxresdefault.jpg',
    youtubeURL: 'https://www.youtube.com/embed/RNi_sB7pdvg',
    creator: 'Its Me',
    likes: 0,
    views: 0
  },
  {
    id: 4,
    title: 'God of War Part 4',
    thumbnail:
      'https://i.ytimg.com/vi/2QO8k2yN7z0/maxresdefault.jpg',
    youtubeURL: 'https://www.youtube.com/embed/npqE9E_hRnw',
    creator: 'Its Me',
    likes: 0,
    views: 0
  },
  {
    id: 5,
    title: 'God of War Part 5',
    thumbnail:
      'https://i.ytimg.com/vi/cfdhVvcfDrU/maxresdefault.jpg',
    youtubeURL: 'https://www.youtube.com/embed/sjiBbgpbnhI',
    creator: 'Its Me',
    likes: 0,
    views: 0
  }
]
export default {
  name: 'VideoPlayer',
  data () {
    return {
      videos,
      activeVideo: videos[0]
    }
  },
  methods: {
    chooseVideo (video) {
      this.activeVideo = video
      video.views += 1
    },
    addLike () {
      this.activeVideo.likes += 1
    }
  }
}
</script>

<style scoped>
  .thumbnail{
    display: flex;
}
.thumbnail img{
  width: 168px;
}
.thumbnail-info{
  margin-left: 20px;
}
.thumbnail h3{
  font-size: 16px;
}
.thumbnail-views{
  font-size: 14px;
}
h3,
p{
  font-size: 14px;
  margin: 0;
  padding: 0;
}
.video-player{
    display:flex;
    width:1200px;
    margin:auto;
}

.video-container{
    margin-right:40px;
}

.row{
    display:flex;
    justify-content:space-between;
}

button{
    background:#D0021B;
    color:white;
    border:none;
    padding:10px 20px;
}

</style>
