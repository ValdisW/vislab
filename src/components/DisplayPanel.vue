<template>
    <div id="display-panel">
        <p>canvas宽度:<span>{{displayWidth}}</span></p>
        <p>canvas高度:<span>{{displayHeight}}</span></p>
        <canvas id="this.canvasDOM" :class="displayWidth" width="500" height="500"></canvas>
    </div>
</template>

<script>
import * as THREE from 'three'
import OrbitControls from 'three-orbitcontrols'

export default {
    name: 'DisplayPanel',
    props: {
        displayWidth: Number,
        displayHeight: Number
    },
    data() {
        return {
            canvasDOM: null,

            scene: null,
            camera: null,
            renderer: null,

            testMesh: null,
            testLight: null,

            helper: null,
            controls: null
        }
    },
    methods: {
        init: function() {
            this.canvasDOM = document.getElementById('container');
            console.log(this.displayWidth, this.displayHeight);
            this.canvasDOM.setAttribute('width', this.displayWidth);
            this.canvasDOM.setAttribute('height', this.displayHeight);

            this.scene = new THREE.Scene();
            this.scene.background = new THREE.Color(0xffffff);
            this.camera = new THREE.PerspectiveCamera(75, this.canvasDOM.clientWidth / this.canvasDOM.clientHeight, 0.1, 10000);
            this.renderer = new THREE.WebGLRenderer({
                canvas: document.getElementById('this.canvasDOM'),
                antialias: true
            });
            this.renderer.setSize(this.canvasDOM.clientWidth, this.canvasDOM.clientHeight);

            this.camera.position.set(0, 0, 5);

            this.controls = new OrbitControls(this.camera, this.canvasDOM);

            this.helper = new THREE.AxesHelper(20, 20, 20);
            this.scene.add(this.helper);

            this.testLight = new THREE.DirectionalLight(0xffffff, 0.8);
            this.testLight.position.set(1, 2, 3);
            this.scene.add(this.testLight);
            
            let testMaterial = new THREE.MeshLambertMaterial({color: 0xff0000});
            let testGeometry = new THREE.BoxGeometry(1,2 ,3);
            this.testMesh = new THREE.Mesh(testGeometry, testMaterial);

            this.scene.add(this.testMesh);
        },
        animate: function(){
            requestAnimationFrame(this.animate);
            this.renderer.render(this.scene, this.camera);
            this.testMesh.rotation.x += 0.01;
            this.testMesh.rotation.y += 0.01;
            this.testMesh.rotation.z += 0.01;
        }
    },
    mounted() {
        console.log('mounted');
        this.init();
        this.animate();
    },
    updated(){
        console.log('updated');
        console.log('displaywidth:', this.displayWidth);
    }
}
</script>
