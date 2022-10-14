# 🧩 CANNON.JS Tutorial

Cannon.js is a Javascript library to simulate real-world physics.

It is a physics engine to be paired with other libraries like Three.js to imitate real-world phenomenons like gravity, friction, collision, inertia, etc.

## 🪜 HOW TO STEPS:

### 1. Creation of a CANNON Physics World

```js
const world = new CANNON.World({
  gravity: new CANNON.Vec3(0, -9.81, 0),
});
```

### 2. Creation of a THREE Mesh

```js
const boxGeo = new THREE.BoxGeometry(2, 2, 2);
const boxMat = new THREE.MeshBasicMaterial({
  color: 0x00ff00,
  wireframe: true,
});
const boxMesh = new THREE.Mesh(boxGeo, boxMat);
scene.add(boxMesh);
```

### 3. Creation of a CANNON Body

The CANNON Body is a transparent entity which is affected by physical phenomenons of the CANNON World.

```js
const boxBody = new CANNON.Body({
  mass: 1,
  shape: new CANNON.Box(new CANNON.Vec3(1, 1, 1)),
  position: new CANNON.Vec3(5, 20, 0),
});
world.addBody(boxBody);
```

### 4. Merge: THREE Mesh and CANNON Physics Body

```js
function animate() {
  boxMesh.position.copy(boxBody.position);
  boxMesh.quaternion.copy(boxBody.quaternion);
}
```

## 📜 References:

- Tutorial followed: [link](https://youtu.be/TPKWohwHrbo)
