<template>
    <div id="display-panel">
        <canvas id="container"></canvas>
    </div>
</template>

<script>
import * as THREE from 'three'
import OrbitControls from 'three-orbitcontrols'

export default {
    name: 'DisplayPanel',
    props: {
        width: Number,
        height: Number
    },
    data() {
        return {
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
            const container = document.getElementById('container');
            container.setAttribute('width', parseInt(this.width));
            container.setAttribute('height', parseInt(this.height));

            this.scene = new THREE.Scene();
            this.scene.background = new THREE.Color(0xffffff);
            this.camera = new THREE.PerspectiveCamera(75, container.clientWidth / container.clientHeight, 0.1, 10000);
            this.renderer = new THREE.WebGLRenderer({
                canvas: document.getElementById('container'),
                antialias: true
            });
            this.renderer.setSize(container.clientWidth, container.clientHeight);

            this.camera.position.set(0, 0, 5);

            this.controls = new OrbitControls(this.camera, container);

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
        this.init();
        this.animate();
    }
}
</script>

<style scoped>
    /* #container{
        height: 400px;
    } */
</style>

