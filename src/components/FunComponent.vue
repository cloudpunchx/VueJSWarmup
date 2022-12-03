<template>
    <div>
        <article>

        </article>
        <button>Click me!</button>
    </div>
</template>

<!-- need to fix, cant get p tags on page -->

<script>
    export default {
        name :  "FunComponent",
        data() {
            return {
                isBlue : false,
                secrets : ['Her hair is full of secrets', 
                            'Secret 2', 
                            'Secret 3'
                        ]
            }
        },
        methods: {
            makeBlue() {
                if (this.isBlue){
                    document.body.style.backgroundColor = "white";
                    document.querySelector(`article`).style.color = "black";
                    // this.isBlue = false
                } else{
                    document.body.style.backgroundColor = "lightblue";
                    document.querySelector(`article`).style.color = "white";
                    // this.isBlue = true
                }
                // commented code is equivalent to this flipped boolean below
                this.isBlue = !this.isBlue;
            },
            // how to change text on the CLICKED P tag
            changeText(event){
                let target = event.target;
                target.style.color = "pink";
            },
            addSecret() {
                for (let secret of this.secrets){
                    document.querySelector(`article`).insertAdjacentHTML(`beforeend`, `<p>${secret}</p>`)
                }
                let tags = document.querySelectorAll(`p`);
                for (let p of tags){
                    p.addEventListener(`click`, this.changeText);
                }
            }
        },
        // if you want the element to be already loaded with these changes made, you could call functions in CREATED
        // but you cant select items from a page that isnt Mounted so it might not work depending
        // created () {
        //     ;
        // },
        mounted () {
            document.querySelector('button').addEventListener(`click`, this.makeBlue);
            this.addSecret();
        },
    }
</script>

<style scoped>

</style>