<template>
<div class="hero is-info is-bold is-fullheight">
    <div class="hero-body">
        <div class="container">
            <h1 class="title">こんにちは</h1>
            <div v-if="flag">
              <h2 v-if="flag" class="subtitle"> {{ displayName }} </h2>
            </div>
            <div v-else>
                <button class="button is-primary is-outlined" @click="flag = !flag" >Click me</button>
            </div>
        </div>
    </div>
    <div class="hero-foot">
    </div>
</div>
</template>

<script>
export default{
    computed: {
        count () { return this.$store.state.counter.count }
    },
    data(){
        return{
            displayName: 'onsd',
            flag: false
        }
    },
    methods:{
        getProfile(){
            flag = !flag
            liff.getProfile().then((profile) => {
                this.displayName = profile.displayName
            }).catch(function (error){
                alert("Error getting profile: " + error)
            });
        },
        addCount (e) {
            this.$store.commit('counter/add')
        }
    }
}
</script>

