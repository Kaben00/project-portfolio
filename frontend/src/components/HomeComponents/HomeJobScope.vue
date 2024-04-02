<template>
    <div>
        <span class="typing-item">&nbsp;{{ currentType }}</span>
        <span class="type-line"></span>
    </div>
</template>

<script>
    export default {
        data : () => ({
            jobItems : ['Frontend Developer', 'WordPress Developer'],
            currentJobItems : 0,
            currentType : '',
            isDeleting : false,
            typingSpeed : 100,
            pauseTime : 3000,
        }),

        mounted() {
            this.processTyping()
        },

        methods : {
            processTyping() {
                const current = this.jobItems[this.currentJobItems % this.jobItems.length]
                let timeout = this.typingSpeed

                if (this.isDeleting) {
                    this.currentType = current.substring(0, this.currentType.length - 1)
                }

                if (!this.isDeleting) {
                    this.currentType = current.substring(0, this.currentType.length + 1)
                }

                if (!this.isDeleting && this.currentType === current) {
                    timeout = this.pauseTime
                    this.isDeleting = true
                }

                if (this.isDeleting && this.currentType === '') {
                    this.isDeleting = false
                    this.currentJobItems++
                }

                setTimeout(() => this.processTyping(), timeout)
            }
        }
    }
</script>

<style scoped>
    @keyframes blinking {
        from, to { border-color:  transparent }
        50% { border-color: #0563bb }
    }

    @keyframes typing {
        from { width: 0}
        to { width: 100% }
    }

    .type-line {
        overflow: hidden;
        border-right: 1px solid #0563bb;
        white-space: nowrap;
        margin: 0 auto;
        letter-spacing: 50px;
        animation: typing 3.5s steps(30, end), blinking 1.5s step-end infinite;
    }

    .typing-item {
        color: #0563bb;
        letter-spacing: 1px;
    }
</style>