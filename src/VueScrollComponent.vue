<template>
    <transition name="top-scroll-fade">
        <div class="top-scroll"
             :style="`bottom:${this.bottom};right:${this.right};`"
             v-show="visible"
             v-on:click="scrollToTop">
            <div class="default">
                <button class="top-scroll-button"
                        :style="`background-color:${this.color};height:${this.size};width:${this.size}`">
                    <i :class="`${this.icon} top-scroll-icon`"
                       :style="`font-size:${this.font};color:${this.fontcolor}`">
                    </i>
                </button>
            </div>
        </div>
    </transition>
</template>

<script>
    export default {
        name: 'scrollToTop',

        props: {
            color: {
                type: String,
                default: '#e91e63'
            },
            icon: {
                type: String,
                default: 'far fa-angle-up'
            },
            size: {
                type: String,
                default: '60px'
            },
            font: {
                type: String,
                default: '32px'
            },
            fontcolor: {
                type: String,
                default: '#fff'
            },
            visibleoffset: {
                type: [String, Number],
                default: 600
            },
            right: {
                type: String,
                default: '50px',
            },
            bottom: {
                type: String,
                default: '80px',
            }
        },

        data () {
            return {
                visible: false
            }
        },

        mounted () {
            window.smoothscroll = () => {
                let currentScroll = document.documentElement.scrollTop || document.body.scrollTop
                if (currentScroll > 0) {
                    window.requestAnimationFrame(window.smoothscroll)
                    window.scrollTo(0, Math.floor(currentScroll - (currentScroll / 5)))
                }
            }
            window.addEventListener('scroll', this.catchScroll)
        },

        destroyed () {
            window.removeEventListener('scroll', this.catchScroll)
        },

        methods: {
            catchScroll () {
                this.visible = (window.pageYOffset > parseInt(this.visibleoffset))
            },

            scrollToTop () {
                window.smoothscroll()
                this.$emit('scrolled');
            }
        }
    }
</script>

<style scoped>

    .top-scroll {
        position: fixed;
        z-index: 1000;
        cursor: pointer;
    }

    .top-scroll-button {
        outline: none !important;
        border-radius: 50%;
        cursor: pointer;
        border: none;
        opacity: 0.8;
    }

    .top-scroll-button:hover {
        opacity: 1;
    }

    .top-scroll-icon {
        vertical-align: middle;
    }

    .top-scroll-fade-enter-active, .top-scroll-fade-leave-active {
        transition: opacity 1s;
    }

    .top-scroll-fade-enter, .top-scroll-fade-leave-to {
        opacity: 0;
    }

</style>

