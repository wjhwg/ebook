<template>
    <div class="ebook-reader">
        <!-- {{$route.params.fileName}} -->
        <div id="read"></div>
    </div>
</template>
<script>
    import {mapGetters} from 'vuex'
    import Epub from 'epubjs'
    global.ePub = Epub
    export default {
        computed: {
            ...mapGetters(['fileName'])
        },
        mounted() {
            const fileName = this.$route.params.fileName
            this.$store.dispatch('setFileName', fileName).then(() => {
                this.initEPub()
            })
        },
        methods: {
            initEPub(){
                const url = 'http://192.168.1.103:9000/epub/epub/Biomedicine/' + this.fileName + '.epub'
                this.book = new Epub(url);
                this.rendetation = this.book.renderTo(read, {
                    width: innerWidth,
                    height: innerHeight,
                    method: 'default'
                })
                this.rendetation.display()
                console.log(this.book)
            }
        },
    }
</script>
<style lang="scss" scoped>

</style>
    