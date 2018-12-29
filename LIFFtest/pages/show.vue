<template>
    <div class="hero is-info is-bold is-fullheight">
        <div class="hero-body">
            <div class="container">
                <h1 class="title is-full">こんにちは、{{ displayName }}</h1>
                <button class="button is-primary is-outlined" @click="getProfile();flag = !flag" >
                    Click me
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      userId: 'userID',
      displayName: '',
      pictureUrl: 'https://bulma.io/images/placeholders/128x128.png',
      statusMessage: ''
    }
  },
  methods: {
    getProfile() {
    
        liff.getProfile().then((profile) => {
            this.userId = profile.userId
            this.displayName = profile.displayName
            this.pictureUrl = profile.pictureUrl
            this.statusMessage = profile.statusMessage
        
      }).catch(function (error) {
        alert("Error getting profile: " + error);
      });
    }
  }
}
</script>