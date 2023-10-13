<template>
    <main class="display-flex">
        <section class="display-flex intro-sect">
            <div class="text-div">
                <h1 id="tag_one">Lorem ispum dolor</h1>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. 
                    Ea recusandae nesciunt, a qui placeat nobis voluptate,
                    assumenda odio minus, ex quam unde error!
                     Facilis animi perspiciatis inventore.
                </p>
                <Control :firstButton="btn1_state" :secondButton="btn2_state" @btnClick="btnState"/>
            </div>
            <div class="img-div" >
                <span>
                    <img src="../assets/img/gavi.jpg" alt="player image" class="img">
                </span>
            </div>
        </section>
        <section class="details-sect">
            <h1>Lorem ispum dolor</h1>
            <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. 
                Ea recusandae nesciunt, a qui placeat nobis voluptate,
                assumenda odio minus, ex quam unde error!
                    Facilis animi perspiciatis inventore.
            </p> 
            <div class="display-flex">
                <div class="details-sect-control-div">
                    <Control :firstButton="btn3_state" :secondButton="btn4_state" @btnClick="btnState" />
                </div>
                <div class="details-sect-control-div">
                    <Control :firstButton="btn5_state" :secondButton="btn6_state" @btnClick="btnState" />
                </div> 
            </div>
        </section>

        <section class="team-sect">
            <img src="../assets/img/team.jpg" alt="Team Image" class="team-img">
        </section>

        <section class="comment-sect">
            <div class="text-sect">
                <h1>Lorem ispum dolor</h1>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. 
                    Ea recusandae nesciunt, a qui placeat nobis voluptate,
                    assumenda odio minus, ex quam unde error!
                     Facilis animi perspiciatis inventore.
                </p>
            </div>
            <div class="comment-sect-img-div">
                <img src="../assets/img/messi.jpg" alt="Player Image" class="img">
            </div>
        </section>
    </main>
</template>

<script>
    import Control from '../components/Control.vue';
    import { ref } from 'vue'
    export default {
        name:'blog',
        components: {
            Control
        },

        setup(){
            const btn1_state = ref( 'off-state btn1' );
            const btn2_state = ref( 'off-state btn2' );
            const btn3_state = ref( 'off-state btn3' );
            const btn4_state = ref( 'off-state btn4' );
            const btn5_state = ref( 'off-state btn5' );
            const btn6_state = ref( 'off-state btn6' );

            function setBtnState( btn, current_state, btn_val ){
                let reset
                if ( current_state == 'off-state') {
                    reset = 'on-state '
                    reset += btn_val
                    btn.value = reset
                } 
                else {
                    reset = 'off-state '
                    reset += btn_val
                    btn.value = reset
                }
            }

            function btnState( btn_description ){

                let space_index = btn_description.indexOf( ' ' )
                let state = btn_description.substr( 0, space_index)
                let clicked_btn = btn_description.substr( space_index + 1, btn_description.length )

                if( clicked_btn === "btn1" ){ 
                    setBtnState( btn1_state, state, clicked_btn )                  
                }
                if( clicked_btn === "btn2" ){                    
                    setBtnState( btn2_state, state, clicked_btn ) 
                }
                if( clicked_btn === "btn3" ){                    
                    setBtnState( btn3_state, state, clicked_btn ) 
                }
                if( clicked_btn === "btn4" ){                    
                    setBtnState( btn4_state, state, clicked_btn ) 
                }
                if( clicked_btn === "btn5" ){                    
                    setBtnState( btn5_state, state, clicked_btn )
                }
                if( clicked_btn === "btn6" ){                    
                    setBtnState( btn6_state, state, clicked_btn )
                }
            }

            return{
                btn1_state,
                btn2_state,
                btn3_state,
                btn4_state,
                btn5_state,
                btn6_state,
                setBtnState,
                btnState
            }
        }
    }
</script>