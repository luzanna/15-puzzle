<template>
    <div class="game">
        <div class="info">
            <h2 class="header">15-puzzle</h2>
            <div class="win">
                <transition name="bounce">
                    <p v-if="message">
                        Puzzle complete!
                    </p>
                </transition>
            </div>
            <div class="item-info">
                <svg xml:space="preserve" viewBox="0 0 100 100" y="0" x="0" xmlns="http://www.w3.org/2000/svg" id="Layer_1" version="1.1" width="128px" height="128px" xmlns:xlink="http://www.w3.org/1999/xlink" style="width:100%;height:100%;background-size:initial;background-repeat-y:initial;background-repeat-x:initial;background-position-y:initial;background-position-x:initial;background-origin:initial;background-image:initial;background-color:rgb(49, 50, 58);background-clip:initial;background-attachment:initial;animation-play-state:paused" ><g class="ldl-scale" style="transform-origin:50% 50%;transform:scale(0.8);animation-play-state:paused" ><g style="animation-play-state:paused" ><path stroke-miterlimit="10" stroke-width="3.5" stroke="#323232" fill="#f7b26a" d="M71.41 54.5h-5.727a3 3 0 1 1 0-6h5.727c7.247 0 13.594-5.146 15.093-12.237.281-1.333-.049-2.705-.908-3.764s-2.132-1.666-3.495-1.666H65.683a3 3 0 1 1 0-6H82.1a10.46 10.46 0 0 1 8.156 3.887 10.458 10.458 0 0 1 2.117 8.783C90.292 47.352 81.476 54.5 71.41 54.5z" style="stroke:rgb(50, 50, 50);fill:rgb(247, 178, 106);animation-play-state:paused" ></path></g>
                    <g opacity=".2" style="animation-play-state:paused" ><path d="M71.41 53.5h-5.727a3 3 0 1 1 0-6h5.727c7.247 0 13.594-5.146 15.093-12.237.281-1.333-.049-2.705-.908-3.764s-2.132-1.666-3.495-1.666H65.683a3 3 0 1 1 0-6H82.1a10.46 10.46 0 0 1 8.156 3.887 10.458 10.458 0 0 1 2.117 8.783C90.292 46.352 81.476 53.5 71.41 53.5z" style="animation-play-state:paused" ></path></g>
                    <g style="animation-play-state:paused" ><path stroke-miterlimit="10" stroke-width="3.5" stroke="#323232" fill="#f7b26a" d="M50.333 60s14.833 10.82 14.833 24.167H35.5C35.5 70.82 50.333 60 50.333 60z" style="stroke:rgb(50, 50, 50);fill:rgb(247, 178, 106);animation-play-state:paused" ></path></g>
                    <path opacity=".2" d="M55.32 83.167h9.846C65.167 69.82 50.333 59 50.333 59s-1.783 1.302-4.112 3.556c3.747 4.879 8.167 12.229 9.099 20.611z" style="animation-play-state:paused" ></path>
                    <g style="animation-play-state:paused" ><path stroke-miterlimit="10" stroke-width="3.5" stroke="#323232" fill="#f7b26a" d="M34.317 54.5H28.59c-10.066 0-18.882-7.148-20.963-16.997a10.457 10.457 0 0 1 2.117-8.783 10.458 10.458 0 0 1 8.156-3.887h16.417a3 3 0 1 1 0 6H17.9c-1.363 0-2.637.607-3.495 1.666s-1.189 2.431-.908 3.764C14.996 43.354 21.343 48.5 28.59 48.5h5.727a3 3 0 1 1 0 6z" style="stroke:rgb(50, 50, 50);fill:rgb(247, 178, 106);animation-play-state:paused" ></path></g>
                    <path stroke-miterlimit="10" stroke-width="3.5" stroke="#323232" fill="#f7b26a" d="M50 66.167c16.384 0 29.667-21.64 29.667-48.333H20.333c0 26.693 13.283 48.333 29.667 48.333z" style="stroke:rgb(50, 50, 50);fill:rgb(247, 178, 106);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-width="3.5" stroke="#323232" fill="#fff" d="M50.719 27.675l3.242 6.568a.801.801 0 0 0 .604.439l7.249 1.053c.658.096.92.904.444 1.367l-5.245 5.113a.804.804 0 0 0-.231.71l1.238 7.219a.802.802 0 0 1-1.163.845l-6.483-3.409a.8.8 0 0 0-.746 0l-6.483 3.409a.801.801 0 0 1-1.163-.845l1.238-7.219a.802.802 0 0 0-.231-.71l-5.245-5.113a.801.801 0 0 1 .444-1.367l7.249-1.053a.803.803 0 0 0 .604-.439l3.242-6.568a.8.8 0 0 1 1.436 0z" style="stroke:rgb(50, 50, 50);fill:rgb(255, 255, 255);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-width="3.5" stroke="#fff" fill="#f7b26a" stroke-linecap="round" d="M27.829 35.411c.065.218.13.435.197.651" style="stroke:rgb(255, 255, 255);fill:rgb(247, 178, 106);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-width="3.5" stroke="#fff" fill="#f7b26a" stroke-linecap="round" d="M25.401 22.903a71.583 71.583 0 0 0 1.017 6.788" style="stroke:rgb(255, 255, 255);fill:rgb(247, 178, 106);animation-play-state:paused" ></path>
                    <path opacity=".2" d="M65.042 16.833c-1.286 23.562-12.945 42.251-27.49 43.872 3.786 2.856 8.001 4.461 12.448 4.461 16.384 0 29.667-21.64 29.667-48.333H65.042z" style="animation-play-state:paused" ></path>
                    <metadata xmlns:d="https://loading.io/stock/" style="animation-play-state:paused" ><d:name style="animation-play-state:paused" >trophy</d:name>
                        <d:tags style="animation-play-state:paused" >trophy,bowl,best,first,winner,success,prize,award</d:tags>
                        <d:license style="animation-play-state:paused" >by</d:license>
                        <d:slug style="animation-play-state:paused" >d4apaa</d:slug></metadata></g><!-- generated by https://loading.io/ --></svg>
                <div class="item-data"> {{victory}} </div>
            </div>
            <div class="item-info">
                <svg xml:space="preserve" viewBox="0 0 100 100" y="0" x="0" xmlns="http://www.w3.org/2000/svg" id="圖層_1" version="1.1" width="128px" height="128px" xmlns:xlink="http://www.w3.org/1999/xlink" style="width:100%;height:100%;background-size:initial;background-repeat-y:initial;background-repeat-x:initial;background-position-y:initial;background-position-x:initial;background-origin:initial;background-image:initial;background-color:rgb(49, 50, 58);background-clip:initial;background-attachment:initial;animation-play-state:paused" ><g class="ldl-scale" style="transform-origin:50% 50%;transform:scale(0.8);animation-play-state:paused" ><g style="animation-play-state:paused" ><path fill="#f47e60" d="M92.5 33.3L76.3 17.1v11.1H57.9c-4.2 0-8 1.3-11.2 3.5 2.3 2.5 4.1 5.6 5 9.1 1.7-1.4 3.8-2.3 6.2-2.3h18.4v11.1l16.2-16.3z" style="fill:rgb(127, 116, 91);animation-play-state:paused" ></path>
                    <path fill="#f47e60" d="M28.6 61.6H7.5v10.2h21.1c4.5 0 8.6-1.3 11.8-3.5-2.3-2.5-4.1-5.6-5.2-8.9-1.7 1.4-4.2 2.2-6.6 2.2z" style="fill:rgb(127, 116, 91);animation-play-state:paused" ></path></g>
                    <path fill="#333" d="M92.5 66.7L76.3 50.5v11.1H57.9c-5.2 0-9.5-4.2-9.5-9.5V47c0-.6 0-1.3-.1-1.9 0-.3-.1-.5-.1-.8 0-.4-.1-.7-.2-1-.1-.3-.2-.6-.2-1-.1-.3-.1-.5-.2-.8-.1-.4-.2-.7-.4-1.1-.1-.2-.1-.4-.2-.5-.2-.4-.3-.8-.5-1.2-.1-.1-.1-.2-.2-.4-.2-.4-.4-.8-.7-1.2 0-.1-.1-.1-.1-.2l-.9-1.2s0-.1-.1-.1c-.7-.9-1.5-1.8-2.4-2.6l-.1-.1c-.5-.4-.9-.8-1.4-1.1-.1 0-.1-.1-.2-.1l-1.5-.9c-.1-.1-.2-.1-.3-.2-.5-.3-1-.5-1.5-.7-.1-.1-.3-.1-.4-.2-.5-.2-1-.4-1.4-.5-.2-.1-.3-.1-.5-.2-.5-.1-1-.3-1.4-.4-.2 0-.4-.1-.6-.1-.5-.1-1-.2-1.5-.2-.2 0-.4-.1-.6-.1-.7-.1-1.4-.1-2.2-.1h-21v10.2h21.1c4.8 0 9.6 2.9 9.6 8.6V52c0 .7 0 1.3.1 2 0 .3.1.6.1.9 0 .3.1.7.1 1l.3 1.2c.1.2.1.4.2.6.1.5.3.9.5 1.4 0 .1.1.2.1.3.2.5.4 1 .7 1.5 0 0 0 .1.1.1l.9 1.5c1.4 2.1 3.1 4 5.2 5.4.5.4 1 .7 1.6 1 0 0 .1 0 .1.1.5.3 1 .6 1.6.8.1 0 .1.1.2.1.5.2 1 .4 1.6.6.1 0 .2.1.3.1.5.2 1 .3 1.5.4.1 0 .3.1.4.1.5.1 1 .2 1.5.2.2 0 .3.1.5.1.5.1 1 .1 1.6.1h18.9v11.1l16.2-15.9z" style="fill:rgb(191, 169, 91);animation-play-state:paused" ></path>
                    <metadata xmlns:d="https://loading.io/stock/" style="animation-play-state:paused" ><d:name style="animation-play-state:paused" >random</d:name>
                        <d:tags style="animation-play-state:paused" >shuffle,switch,cross,arrow,turn,random,web application</d:tags>
                        <d:license style="animation-play-state:paused" >by</d:license>
                        <d:slug style="animation-play-state:paused" >6ay2i1</d:slug></metadata></g><!-- generated by https://loading.io/ --></svg>                <div class="item-data">{{steps}}</div>
            </div>
            <div class="item-info">
                <svg xml:space="preserve" viewBox="0 0 100 100" y="0" x="0" xmlns="http://www.w3.org/2000/svg" id="圖層_1" version="1.1" width="128px" height="128px" xmlns:xlink="http://www.w3.org/1999/xlink" style="width:100%;height:100%;background-size:initial;background-repeat-y:initial;background-repeat-x:initial;background-position-y:initial;background-position-x:initial;background-origin:initial;background-image:initial;background-color:rgb(49, 50, 58);background-clip:initial;background-attachment:initial;animation-play-state:paused" ><g class="ldl-scale" style="transform-origin:50% 50%;transform:scale(0.8);animation-play-state:paused" ><path stroke-miterlimit="10" stroke-width="3.5" stroke="#333" fill="#fff" d="M73.195 26.731V14.476h-46.39v12.255c0 5.892 3.877 11.092 9.81 14.252 3.551 1.892 5.674 4.955 5.674 8.231v1.571c0 3.277-2.123 6.34-5.674 8.231-5.933 3.161-9.81 8.361-9.81 14.252v12.255h46.389V73.269c0-5.892-3.877-11.092-9.81-14.252-3.551-1.892-5.674-4.955-5.674-8.231v-1.571c0-3.277 2.123-6.34 5.674-8.231 5.934-3.161 9.811-8.361 9.811-14.253z" style="stroke:rgb(51, 51, 51);fill:rgb(255, 255, 255);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-linejoin="round" stroke-width="3.5" stroke="#333" fill="#f5e6c8" d="M34.992 85.285h30.017v-8.379c0-3.162-2.139-6.115-5.868-8.102l-.142-.076c-5.55-3.006-12.447-3.006-17.997 0a6.388 6.388 0 0 1-.142.076c-3.729 1.987-5.868 4.94-5.868 8.102v8.379z" style="stroke:rgb(51, 51, 51);fill:rgb(245, 230, 200);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-linejoin="round" stroke-width="3.5" stroke="#333" fill="#f5e6c8" d="M35.162 28.182c.55 2.601 2.548 4.973 5.698 6.652 4.743 2.526 7.979 6.398 9.14 10.761 1.161-4.363 4.398-8.235 9.14-10.761 3.15-1.679 5.148-4.05 5.698-6.652H35.162z" style="stroke:rgb(51, 51, 51);fill:rgb(245, 230, 200);animation-play-state:paused" ></path>
                    <path d="M50 51.645v2.078" stroke-miterlimit="10" stroke-linejoin="round" stroke-linecap="round" stroke-width="3.5" stroke="#333" fill="none" style="stroke:rgb(51, 51, 51);animation-play-state:paused" ></path>
                    <path d="M50 59.87h0" stroke-miterlimit="10" stroke-linejoin="round" stroke-linecap="round" stroke-width="3.5" stroke="#333" fill="none" style="stroke:rgb(51, 51, 51);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-linecap="round" stroke-width="3.5" stroke="#e0e0e0" fill="#fff" d="M32.679 70.839c-.211.44-.399.887-.564 1.343" style="stroke:rgb(224, 224, 224);fill:rgb(255, 255, 255);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-linecap="round" stroke-width="3.5" stroke="#e0e0e0" fill="#fff" d="M43.5 60.893a12.876 12.876 0 0 1-2.385 1.623c-2.051 1.093-3.856 2.429-5.341 3.953" style="stroke:rgb(224, 224, 224);fill:rgb(255, 255, 255);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-width="3.5" stroke="#333" fill="#849b87" d="M80.488 80.41H19.512c-1.66 0-2.887 1.359-2.51 2.78l.682 2.562C18.346 88.24 20.871 90 23.78 90h52.44c2.909 0 5.435-1.76 6.097-4.249l.682-2.562c.377-1.42-.85-2.779-2.511-2.779z" style="stroke:rgb(51, 51, 51);fill:rgb(177, 119, 23);animation-play-state:paused" ></path>
                    <path stroke-miterlimit="10" stroke-width="3.5" stroke="#333" fill="#849b87" d="M80.488 19.59H19.512c-1.66 0-2.887-1.359-2.51-2.78l.682-2.562C18.346 11.76 20.871 10 23.78 10h52.44c2.909 0 5.435 1.76 6.097 4.249l.682 2.562c.377 1.42-.85 2.779-2.511 2.779z" style="stroke:rgb(51, 51, 51);fill:rgb(177, 119, 23);animation-play-state:paused" ></path>
                    <path opacity=".2" d="M80.488 78.659h-5.543v-5.39c0-6.31-4.014-12.215-10.737-15.798-2.973-1.583-4.747-4.083-4.747-6.687v-1.57c0-2.604 1.774-5.104 4.747-6.688 6.723-3.582 10.737-9.487 10.737-15.797v-5.39h5.543c1.397 0 2.715-.629 3.524-1.682.734-.954.98-2.156.676-3.299l-.681-2.562c-.869-3.267-4.072-5.549-7.788-5.549H50v83.5h26.22c3.716 0 6.919-2.282 7.788-5.549l.682-2.562a3.782 3.782 0 0 0-.677-3.299c-.81-1.049-2.127-1.678-3.525-1.678z" style="animation-play-state:paused" ></path>
                    <path d="M23.375 14.795h7.75" stroke-miterlimit="10" stroke-linecap="round" stroke-width="3.5" stroke="#e0e0e0" fill="none" style="stroke:rgb(224, 224, 224);animation-play-state:paused" ></path>
                    <path d="M36.274 14.795h.976" stroke-miterlimit="10" stroke-linecap="round" stroke-width="3.5" stroke="#e0e0e0" fill="none" style="stroke:rgb(224, 224, 224);animation-play-state:paused" ></path>
                    <metadata xmlns:d="https://loading.io/stock/" style="animation-play-state:paused" ><d:name style="animation-play-state:paused" >hourglass</d:name>
                        <d:tags style="animation-play-state:paused" >hourglass,sandglass,timer,countdown,elapse,flow,pass by,temporal</d:tags>
                        <d:license style="animation-play-state:paused" >by</d:license>
                        <d:slug style="animation-play-state:paused" >8jeeja</d:slug></metadata></g><!-- generated by https://loading.io/ --></svg>                <div class="item-data">{{ minutes }} : {{seconds}} </div>
            </div>
            <div class="item-info">
                <button type="submit" class="restart" v-on:click="sortFifteen">
                    <svg xml:space="preserve" viewBox="0 0 100 100" y="0" x="0" xmlns="http://www.w3.org/2000/svg" id="圖層_1" version="1.1" width="128px" height="128px" xmlns:xlink="http://www.w3.org/1999/xlink" style="width:100%;height:100%;background-size:initial;background-repeat-y:initial;background-repeat-x:initial;background-position-y:initial;background-position-x:initial;background-origin:initial;background-image:initial;background-color:rgb(49, 50, 58);background-clip:initial;background-attachment:initial;animation-play-state:paused" ><g class="ldl-scale" style="transform-origin:50% 50%;transform:scale(0.8);animation-play-state:paused" ><path stroke-miterlimit="10" stroke-width="8" stroke="#333" fill="none" d="M76.5 90h-53C16 90 10 84 10 76.5v-53C10 16 16 10 23.5 10h53C84 10 90 16 90 23.5v53C90 84 84 90 76.5 90z" style="stroke:rgb(212, 199, 135);animation-play-state:paused" ></path>
                        <path fill="#77a4bd" d="M75 54.9l-7.8-8.2-8.2 7.7 4.5.1c-1.6 4.8-5.7 8.5-10.8 9.5-3.7.7-7.5 0-10.7-2.2l-3.7 5.5c3.5 2.3 7.5 3.6 11.6 3.6 1.3 0 2.7-.1 4-.4 8.1-1.6 14.4-7.7 16.3-15.7l4.8.1z" style="fill:rgb(191, 169, 91);animation-play-state:paused" ></path>
                        <path fill="#a0c8d7" d="M46 29.5c-8.1 1.6-14.4 7.7-16.3 15.7l-4.7-.1 7.8 8.2 8.2-7.8-4.5-.1c1.6-4.8 5.7-8.5 10.8-9.5 3.7-.7 7.5 0 10.7 2.2l3.7-5.5c-4.7-3-10.2-4.1-15.7-3.1z" style="fill:rgb(127, 116, 91);animation-play-state:paused" ></path>
                        <metadata xmlns:d="https://loading.io/stock/" style="animation-play-state:paused" ><d:name style="animation-play-state:paused" >sync</d:name>
                            <d:tags style="animation-play-state:paused" >sync,reload,fetch,update,refresh,recycle,turn,swap,square,form</d:tags>
                            <d:license style="animation-play-state:paused" >by</d:license>
                            <d:slug style="animation-play-state:paused" >nrlxyp</d:slug></metadata></g><!-- generated by https://loading.io/ --></svg>
                </button>
                <div class="item-data">Play</div>
            </div>
        </div>
        <transition-group name="cube">
            <div class="cube"
                 v-for="item in cubes"
                 v-bind:key="item"
                 v-bind:id="'number' + item"
                 v-on:click="changeCubes(item, cubes)">
                <div class="val" >
                    {{item}}
                </div>
            </div>
        </transition-group>
    </div>
</template>

<script>
    export default {
        name: "fifteen",
        data(){
            return{
                show : true,
                cubes: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16],
                steps: 0,
                victory: 0,
                message: false,
                step: false,
                seconds: 0,
                minutes: 0,
                timer: null,
            }
        },

        mounted() {
                window.onload = this.sortFifteen();
        },

        methods: {

            // сортировка случайным образом + обнуление ходов + запуск таймера
            sortFifteen() {
                let fif = this.cubes;

                fif.sort(() => {
                    return Math.random() - 0.5;
                });

                this.steps = 0;
                this.message = false;
                this.stopTimer();
                this.startTimer();

                return [fif, this.steps];
            },

            // перемещение пятнашек + счет ходов + проверка на решенность, подсчет побед
            changeCubes(item, cubes) {
                if (!this.timer)
                    this.startTimer();

                let index = cubes.indexOf(item);
                let index_next = index + 1;
                let index_previous = index - 1;
                let step = false;

                // если пустая ячейка после нажатого куба и не последняя в строке, меняем
                if (cubes[index_next] === 16 && ((index != 4) || (index != 8) || (index != 12))) {
                    let change = cubes[index];
                    cubes[index] = cubes[index_next];
                    cubes[index_next] = change;
                    step = true;
                }

                // если пустая ячейка до нажатого куба и не первая в строке, меняем
                if (cubes[index_previous] === 16 && ((index != 3) || (index != 7) || (index != 11))) {
                    let change = cubes[index];
                    cubes[index] = cubes[index_previous];
                    cubes[index_previous] = change;
                    step = true;
                }

                // если пустая ячейка снизу, меняем
                if (cubes[index + 4] === 16) {
                    let change = cubes[index];
                    cubes[index] = cubes[index + 4];
                    cubes[index + 4] = change;
                    step = true;
                }

                // если пустая ячейка сверху, меняем
                if (cubes[index - 4] === 16) {
                    let change = cubes[index];
                    cubes[index] = cubes[index - 4];
                    cubes[index - 4] = change;
                    step = true;
                }

                if (step)
                    step = this.steps++;

                this.cubes = cubes;

                if (this.countVictory()) {
                    this.stopTimer();
                }

                return [this.cubes, this.step];
            },

            // таймер
            startTimer() {
                this.timer = setInterval(() => {
                    this.seconds++;
                    if (this.seconds == 60){
                        this.minutes++;
                        this.seconds = 0;
                    }
                }, 1000);
            },

            stopTimer() {
                clearTimeout(this.timer);
                this.timer = null;
                this.seconds = 0;
                this.minutes = 0;
            },

            // счетчик побед
            countVictory() {
                for (let i = 0; i < this.cubes.length - 1; i++) {
                    if ((this.cubes[i + 1] - this.cubes[i]) != 1)
                        return false;
                }
                this.message = true;
                return [this.victory++, this.steps = 0];
            },
        }
    }
</script>

<style scoped>

    .game{
        text-align: center;
        background: #31323a;
        width: 280px;
        height: auto;
        border-radius: 2px;
        color: #c8b212;
        padding: 15px;
        display: block;
    }

    .info{
        display: inline-block;
        width: inherit;
    }

    .header{
        text-align: center;
    }

    .item-info{
        background: #31323a;
        text-align: center;
        width: 25%;
        display:  inline-block;
        padding-bottom: 10px;
    }

    .cube{
        display: inline-block;
        width: 50px;
        height: 50px;
        background: rgba(255, 255, 255, 0.16);
        margin: 5px;
        border-radius: 2px;
        text-align: center;
        font-size: x-large;
    }

    #number16{
        opacity: 0;
    }

    .val{
        padding-top: 10px;
        color: #d9c114;
    }

    .restart{
        background: #31323a;
        outline: none;
        border: none;
        margin-bottom: 5px;
    }

    .start{
        width: 80px;
        height: 80px;
    }

    .cube-move {
        transition: transform 0.2s;
    }

    .bounce-enter-active {
        animation: bounce-in 1s;
    }
    .bounce-leave-active {
        animation: bounce-in 1s reverse;
    }
    @keyframes bounce-in {
        0% {
            transform: scale(0);
        }
        50% {
            transform: scale(1.5);
        }
        100% {
            transform: scale(1);
        }
    }
</style>

