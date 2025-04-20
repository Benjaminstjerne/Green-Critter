<!DOCTYPE html>
<html lang="da">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kvantedyr</title>
    <style>
        body { margin: 0; overflow: hidden; background-color: #000000; touch-action: manipulation; position: relative; }
        canvas { display: block; touch-action: manipulation; position: absolute; top: 0; left: 0; }
    </style>
</head>
<body>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/simplex-noise/2.4.0/simplex-noise.min.js"></script>
    <script>
        const scene = new THREE.Scene();
        scene.background = new THREE.Color(0x000000);
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.body.appendChild(renderer.domElement);

        const simplex = new SimplexNoise();
        const screamingGreen = new THREE.Color(0x39FF14);
        
        // Fuldskærmshåndtering
        let isFullscreen = false;
        let fullscreenButton; // 3D knap til fuldskærm
        
        function toggleFullScreen() {
            if (!document.fullscreenElement) {
                if (document.documentElement.requestFullscreen) {
                    document.documentElement.requestFullscreen();
                } else if (document.documentElement.webkitRequestFullscreen) {
                    document.documentElement.webkitRequestFullscreen();
                } else if (document.documentElement.msRequestFullscreen) {
                    document.documentElement.msRequestFullscreen();
                } else if (document.documentElement.mozRequestFullScreen) {
                    document.documentElement.mozRequestFullScreen();
                }
                isFullscreen = true;
                if (fullscreenButton) {
                    fullscreenButton.visible = false;
                }
            }
        }
        
        // Lyt til fuldskærmsændringer
        document.addEventListener('fullscreenchange', handleFullscreenChange);
        document.addEventListener('webkitfullscreenchange', handleFullscreenChange);
        document.addEventListener('mozfullscreenchange', handleFullscreenChange);
        document.addEventListener('MSFullscreenChange', handleFullscreenChange);
        
        function handleFullscreenChange() {
            isFullscreen = Boolean(document.fullscreenElement || 
                                document.webkitFullscreenElement || 
                                document.mozFullScreenElement || 
                                document.msFullscreenElement);
            if (fullscreenButton) {
                fullscreenButton.visible = !isFullscreen;
            }
        }
        
        function createWildOrganicGeometry(radius, detail, time, additionalNoise = 0) {
            const geometry = new THREE.IcosahedronGeometry(radius, 6);
            const positionAttribute = geometry.getAttribute('position');
            
            for (let i = 0; i < positionAttribute.count; i++) {
                const x = positionAttribute.getX(i);
                const y = positionAttribute.getY(i);
                const z = positionAttribute.getZ(i);
                
                const baseNoise = simplex.noise4D(x * 0.5, y * 0.5, z * 0.5, time * 8.0) * (0.5 + additionalNoise);
                const detailNoise = simplex.noise4D(x * 2, y * 2, z * 2, time * 6.0) * (0.3 + additionalNoise * 0.5);
                const microNoise = simplex.noise4D(x * 4, y * 4, z * 4, time * 4.0) * (0.2 + additionalNoise * 0.3);
                
                const combinedNoise = baseNoise + detailNoise + microNoise;
                
                const waveX = Math.sin(y * 6 + time * 10.0) * (0.15 + additionalNoise * 0.1);
                const waveY = Math.cos(x * 6 + time * 10.0) * (0.15 + additionalNoise * 0.1);
                const waveZ = Math.sin(x * 6 + y * 6 + time * 10.0) * (0.15 + additionalNoise * 0.1);
                
                positionAttribute.setXYZ(
                    i,
                    x * (1 + combinedNoise + waveX),
                    y * (1 + combinedNoise + waveY),
                    z * (1 + combinedNoise + waveZ)
                );
            }
            
            geometry.computeVertexNormals();
            return geometry;
        }

        function getGreenColor(t) {
            return new THREE.Color(
                0.1 + 0.1 * Math.sin(t * 16), 
                0.8 + 0.2 * Math.sin(t * 16 + 2), 
                0.1 + 0.1 * Math.sin(t * 16 + 4)
            );
        }

        // Opret fuldskærmsknap
        function createFullscreenButton() {
            const size = 1.0; // Større for at være let at ramme
            const geometry = createWildOrganicGeometry(size, null, Math.random() * 10);
            const material = new THREE.MeshPhysicalMaterial({
                color: screamingGreen,
                transparent: true,
                opacity: 0.9,
                roughness: 0.7,
                metalness: 0.0,
                clearcoat: 0.1,
                clearcoatRoughness: 0.9,
                reflectivity: 0.2,
                emissive: screamingGreen,
                emissiveIntensity: 1.0, // Lyser mere
                side: THREE.DoubleSide
            });
            const button = new THREE.Mesh(geometry, material);
            
            // Placering i øverste højre hjørne i kameraets synsfelt
            button.position.set(6, 4, 0);
            
            button.userData = {
                isFullscreenButton: true,
                timeOffset: Math.random() * 10,
                pulseIntensity: 0.3 // Ekstra pulsering
            };
            
            scene.add(button);
            return button;
        }

        const objects = [];
        const randomTargets = [];
        
        for (let i = 0; i < 12; i++) {
            const size = 0.5 + Math.random() * 0.5;
            const geometry = createWildOrganicGeometry(size, null, Math.random() * 10);
            const material = new THREE.MeshPhysicalMaterial({
                color: screamingGreen,
                transparent: true,
                opacity: 0.9,
                roughness: 0.7,
                metalness: 0.0,
                clearcoat: 0.1,
                clearcoatRoughness: 0.9,
                reflectivity: 0.2,
                emissive: screamingGreen,
                emissiveIntensity: 0.7,
                side: THREE.DoubleSide
            });
            const mesh = new THREE.Mesh(geometry, material);
            mesh.position.set(
                (Math.random() - 0.5) * 8,
                (Math.random() - 0.5) * 8,
                (Math.random() - 0.5) * 8
            );
            mesh.rotation.set(Math.random() * Math.PI, Math.random() * Math.PI, Math.random() * Math.PI);
            scene.add(mesh);
            objects.push(mesh);
            
            mesh.userData = {
                originalSize: size,
                timeOffset: Math.random() * 10,
                shouldSplit: false,
                splitDelay: 0,
                splitTarget: new THREE.Vector3(),
                lastPosition: new THREE.Vector3()
            };
            
            randomTargets.push(new THREE.Vector3(
                (Math.random() - 0.5) * 10,
                (Math.random() - 0.5) * 10,
                (Math.random() - 0.5) * 10
            ));
        }

        // Opret fuldskærmsknappen
        fullscreenButton = createFullscreenButton();

        const ambientLight = new THREE.AmbientLight(0xffffff, 0.3);
        scene.add(ambientLight);

        const directionalLight = new THREE.DirectionalLight(0xffffff, 0.5);
        directionalLight.position.set(5, 5, 5);
        scene.add(directionalLight);

        const greenPointLight = new THREE.PointLight(0x39FF14, 1, 20);
        greenPointLight.position.set(0, 0, 5);
        scene.add(greenPointLight);

        camera.position.z = 12;

        let interactionX = 0, interactionY = 0;
        let targetInteractionX = 0, targetInteractionY = 0;
        let time = 0;
        let isInteracting = false;
        let lastInteractionTime = 0;
        
        let interactionTracker = {
            wasInteracting: false,
            interactionEndTime: 0,
            lastInteractionPos: new THREE.Vector3(),
            interactionVelocity: new THREE.Vector3()
        };
        
        const virtualCopies = [];
        const maxVirtualCopies = 15; 
        
        // Raycasting for fuldskærmsknap
        const raycaster = new THREE.Raycaster();
        const mouse = new THREE.Vector2();
        
        function updateRandomTargets() {
            if (Math.random() < 0.1) {
                const targetIndex = Math.floor(Math.random() * randomTargets.length);
                randomTargets[targetIndex].set(
                    (Math.random() - 0.5) * 10,
                    (Math.random() - 0.5) * 10,
                    (Math.random() - 0.5) * 10
                );
            }
        }
        
        function createVirtualCopy(sourceObject, targetPosition) {
            const originalSize = sourceObject.userData.originalSize;
            const sizeFactor = Math.random() * 0.5 + 0.6;
            const geometry = createWildOrganicGeometry(originalSize * sizeFactor, null, Math.random() * 10);
            
            const material = new THREE.MeshPhysicalMaterial({
                color: screamingGreen,
                transparent: true,
                opacity: 0.7,
                roughness: 0.7,
                metalness: 0.0,
                clearcoat: 0.1,
                clearcoatRoughness: 0.9,
                reflectivity: 0.2,
                emissive: screamingGreen,
                emissiveIntensity: 0.6,
                side: THREE.DoubleSide
            });
            
            const copy = new THREE.Mesh(geometry, material);
            copy.position.copy(sourceObject.position);
            
            copy.userData = {
                targetPosition: targetPosition,
                sourcePosition: sourceObject.position.clone(),
                lifespan: 60 + Math.floor(Math.random() * 40),
                age: 0,
                speed: 0.06 + Math.random() * 0.1,
                initialOpacity: material.opacity,
                originalSize: originalSize,
                sizeFactor: sizeFactor,
                returningHome: false,
                timeOffset: Math.random() * 10
            };
            
            scene.add(copy);
            return copy;
        }
        
        function updateVirtualCopies() {
            for (let i = virtualCopies.length - 1; i >= 0; i--) {
                const copy = virtualCopies[i];
                copy.userData.age += 1;
                
                copy.geometry.dispose();
                const thisTime = time + copy.userData.timeOffset;
                copy.geometry = createWildOrganicGeometry(
                    copy.userData.originalSize * copy.userData.sizeFactor, 
                    null, 
                    thisTime
                );
                
                if (copy.userData.age > copy.userData.lifespan) {
                    copy.material.opacity = copy.userData.initialOpacity * (1 - (copy.userData.age - copy.userData.lifespan) / 30);
                    copy.scale.multiplyScalar(0.98);
                    
                    if (copy.userData.age > copy.userData.lifespan + 30) {
                        scene.remove(copy);
                        copy.geometry.dispose();
                        copy.material.dispose();
                        virtualCopies.splice(i, 1);
                    }
                    continue;
                }
                
                if (!copy.userData.returningHome && copy.userData.age > copy.userData.lifespan * 0.5 && Math.random() < 0.05) {
                    copy.userData.returningHome = true;
                    copy.userData.targetPosition = copy.userData.sourcePosition.clone();
                    copy.userData.speed *= 1.5;
                }
                
                const direction = new THREE.Vector3().subVectors(
                    copy.userData.targetPosition, 
                    copy.position
                ).normalize();
                
                copy.position.add(direction.multiplyScalar(copy.userData.speed));
                
                copy.rotation.x += 0.01;
                copy.rotation.y += 0.01;
                
                if (copy.position.distanceTo(copy.userData.targetPosition) < 0.8) {
                    if (copy.userData.returningHome) {
                        copy.userData.age = copy.userData.lifespan;
                    } else {
                        const shouldDie = Math.random() < 0.2;
                        
                        if (shouldDie) {
                            copy.userData.age = copy.userData.lifespan;
                        } else {
                            const newTargetIndex = Math.floor(Math.random() * objects.length);
                            const newTarget = objects[newTargetIndex].position.clone();
                            copy.userData.targetPosition = newTarget;
                        }
                    }
                }
            }
            
            if (virtualCopies.length < maxVirtualCopies && Math.random() < 0.08) {
                const sourceIndex = Math.floor(Math.random() * objects.length);
                const sourceObj = objects[sourceIndex];
                
                let targetIndex = Math.floor(Math.random() * objects.length);
                while (targetIndex === sourceIndex && objects.length > 1) {
                    targetIndex = Math.floor(Math.random() * objects.length);
                }
                const targetPos = objects[targetIndex].position.clone();
                
                const virtualCopy = createVirtualCopy(sourceObj, targetPos);
                virtualCopies.push(virtualCopy);
            }
            
            objects.forEach(obj => {
                if (obj.userData.shouldSplit) {
                    obj.userData.splitDelay -= 0.01;
                    
                    if (obj.userData.splitDelay <= 0) {
                        obj.userData.shouldSplit = false;
                        
                        const numCopies = 2 + Math.floor(Math.random() * 2);
                        for (let i = 0; i < numCopies; i++) {
                            if (virtualCopies.length < maxVirtualCopies) {
                                let targetPos = new THREE.Vector3(
                                    obj.position.x + (Math.random() * 2 - 1) * 5,
                                    obj.position.y + (Math.random() * 2 - 1) * 5, 
                                    obj.position.z + (Math.random() * 2 - 1) * 5
                                );
                                
                                const virtualCopy = createVirtualCopy(obj, targetPos);
                                virtualCopies.push(virtualCopy);
                            }
                        }
                    }
                }
            });
        }
        
        function animate() {
            requestAnimationFrame(animate);
            time += 0.01;
            
            let prevInteracting = interactionTracker.wasInteracting;
            
            if (time - lastInteractionTime > 1.5) {
                isInteracting = false;
            }
            interactionTracker.wasInteracting = isInteracting;
            
            if (prevInteracting && !isInteracting) {
                interactionTracker.interactionEndTime = time;
                interactionTracker.lastInteractionPos.set(interactionX * 10, interactionY * 10, 0);
                
                objects.forEach(obj => {
                    const dist = obj.position.distanceTo(interactionTracker.lastInteractionPos);
                    if (dist < 5) {
                        obj.userData.lastPosition.copy(obj.position);
                        obj.userData.shouldSplit = true;
                        obj.userData.splitDelay = 0.1 + Math.random() * 0.2;
                        obj.userData.splitTarget.copy(interactionTracker.lastInteractionPos);
                    }
                });
            }
            
            updateRandomTargets();
            updateVirtualCopies();
            
            // Opdater fuldskærmsknappen
            if (fullscreenButton && fullscreenButton.visible) {
                fullscreenButton.geometry.dispose();
                const buttonTime = time + fullscreenButton.userData.timeOffset;
                fullscreenButton.geometry = createWildOrganicGeometry(
                    1.0, 
                    null, 
                    buttonTime
                );
                
                // Lad knappen rotere og pulsere
                fullscreenButton.rotation.x += 0.01;
                fullscreenButton.rotation.y += 0.01;
                
                const pulseScale = 1 + fullscreenButton.userData.pulseIntensity * Math.sin(time * 2.0);
                fullscreenButton.scale.set(pulseScale, pulseScale, pulseScale);
                
                // Intensiteten pulserer også
                fullscreenButton.material.emissiveIntensity = 0.8 + 0.4 * Math.sin(time * 3.0);
            }

            if (isInteracting) {
                interactionX += (targetInteractionX - interactionX) * 0.95;
                interactionY += (targetInteractionY - interactionY) * 0.95;
            }

            objects.forEach((obj, index) => {
                obj.geometry.dispose();
                const thisTime = time + obj.userData.timeOffset;
                
                let additionalNoise = 0;
                if (obj.userData.shouldSplit) {
                    additionalNoise = 0.2;
                }
                
                obj.geometry = createWildOrganicGeometry(
                    obj.userData.originalSize, 
                    null, 
                    thisTime,
                    additionalNoise
                );

                let targetVector;
                
                if (isInteracting) {
                    targetVector = new THREE.Vector3(interactionX * 10, interactionY * 10, 0);
                } else {
                    targetVector = randomTargets[index];
                }
                
                const distanceToTarget = obj.position.distanceTo(targetVector);

                if (!obj.userData.shouldSplit) {
                    if (distanceToTarget > 0.1) {
                        const direction = new THREE.Vector3().subVectors(targetVector, obj.position).normalize();
                        const movementSpeed = isInteracting ? 
                            0.3 / (1 + distanceToTarget * 0.1) : 
                            0.08 / (1 + distanceToTarget * 0.2);
                        
                        let targetZ;
                        if (isInteracting) {
                            targetZ = 2 - distanceToTarget * 0.6;
                        } else {
                            targetZ = Math.sin(time * 0.6 + index) * 3;
                        }
                        obj.position.z += (targetZ - obj.position.z) * 0.2;
                        
                        obj.position.add(direction.multiplyScalar(movementSpeed));
                    }
                } else {
                    obj.position.x += (Math.random() - 0.5) * 0.02;
                    obj.position.y += (Math.random() - 0.5) * 0.02;
                    obj.position.z += (Math.random() - 0.5) * 0.02;
                }

                obj.rotation.x += 0.005;
                obj.rotation.y += 0.005;
                obj.rotation.z += 0.002;

                if (isInteracting) {
                    const scale = 1 + 0.4 / (1 + distanceToTarget * 0.7);
                    obj.scale.lerp(new THREE.Vector3(scale, scale, scale), 0.15);
                } else {
                    const pulseScale = 1 + 0.2 * Math.sin(time * 1.0 + index);
                    obj.scale.lerp(new THREE.Vector3(pulseScale, pulseScale, pulseScale), 0.15);
                }

                let colorIntensity;
                if (isInteracting) {
                    colorIntensity = 0.6 + 0.6 / (1 + distanceToTarget * 0.2);
                } else {
                    colorIntensity = 0.6 + 0.4 * Math.sin(time * 1.0 + index);
                }
                obj.material.emissiveIntensity = colorIntensity;
                
                if (isInteracting) {
                    obj.material.opacity = 0.6 + 0.4 / (1 + distanceToTarget * 0.3);
                } else {
                    obj.material.opacity = 0.7 + 0.3 * Math.sin(time * 0.8 + index * 0.7);
                }
                
                const baseColor = getGreenColor(time + index * 0.1);
                obj.material.color.lerp(baseColor, 0.15);
                obj.material.emissive.lerp(baseColor, 0.15);
            });

            if (isInteracting) {
                camera.position.x += (interactionX * 2.0 - camera.position.x) * 0.08;
                camera.position.y += (interactionY * 2.0 - camera.position.y) * 0.08;
            } else {
                camera.position.x = Math.sin(time * 0.3) * 2.0;
                camera.position.y = Math.cos(time * 0.3) * 2.0;
            }
            
            if (isInteracting) {
                greenPointLight.position.set(interactionX * 10, interactionY * 10, 5);
            } else {
                greenPointLight.position.set(
                    Math.sin(time * 0.8) * 8,
                    Math.cos(time * 0.8) * 8,
                    5
                );
            }

            renderer.render(scene, camera);
        }

        function updateInteractionPosition(clientX, clientY) {
            targetInteractionX = (clientX / window.innerWidth) * 2 - 1;
            targetInteractionY = -(clientY / window.innerHeight) * 2 + 1;
            isInteracting = true;
            lastInteractionTime = time;
        }

        function onMouseMove(event) {
            updateInteractionPosition(event.clientX, event.clientY);
            
            // Opdater mus-position til raycasting
            mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
            mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
        }

        function onTouchMove(event) {
            if (event.touches.length > 0) {
                updateInteractionPosition(event.touches[0].clientX, event.touches[0].clientY);
                
                // Opdater mus-position til raycasting
                mouse.x = (event.touches[0].clientX / window.innerWidth) * 2 - 1;
                mouse.y = -(event.touches[0].clientY / window.innerHeight) * 2 + 1;
            }
        }

        function onInteractionEnd() {
            lastInteractionTime = time;
        }

        function onClick(event) {
            // Opdater mus-position til raycasting
            mouse.x = (event.clientX / window.innerWidth) * 2 - 1;
            mouse.y = -(event.clientY / window.innerHeight) * 2 + 1;
            
            raycaster.setFromCamera(mouse, camera);
            
            // Tjek om fuldskærmsknappen blev ramt
            if (fullscreenButton && fullscreenButton.visible) {
                const intersects = raycaster.intersectObject(fullscreenButton);
                if (intersects.length > 0) {
                    toggleFullScreen();
                    return;
                }
            }
            
            // Hvis ikke fuldskærmsknap, så fortsæt med normal klik-håndtering
            const interactionVector = new THREE.Vector3(interactionX * 10, interactionY * 10, 0);
            
            objects.forEach(obj => {
                const distanceToInteraction = obj.position.distanceTo(interactionVector);
                if (distanceToInteraction < 3) {
                    for (let i = 0; i < 3; i++) {
                        if (virtualCopies.length < maxVirtualCopies) {
                            const targetIndex = Math.floor(Math.random() * objects.length);
                            const targetPos = objects[targetIndex].position.clone();
                            
                            const virtualCopy = createVirtualCopy(obj, targetPos);
                            virtualCopies.push(virtualCopy);
                        }
                    }
                    
                    obj.material.emissiveIntensity = 1.5;
                    setTimeout(() => {
                        obj.material.emissiveIntensity = 0.7;
                    }, 300);
                }
            });
        }

        function onTouchStart(event) {
            if (event.touches.length > 0) {
                // Opdater mus-position til raycasting
                mouse.x = (event.touches[0].clientX / window.innerWidth) * 2 - 1;
                mouse.y = -(event.touches[0].clientY / window.innerHeight) * 2 + 1;
                
                raycaster.setFromCamera(mouse, camera);
                
                // Tjek om fuldskærmsknappen blev ramt
                if (fullscreenButton && fullscreenButton.visible) {
                    const intersects = raycaster.intersectObject(fullscreenButton);
                    if (intersects.length > 0) {
                        toggleFullScreen();
                        return;
                    }
                }
                
                // Hvis ikke fuldskærmsknap, så fortsæt med normal tryk-håndtering
                const interactionVector = new THREE.Vector3(interactionX * 10, interactionY * 10, 0);
                
                objects.forEach(obj => {
                    const distanceToInteraction = obj.position.distanceTo(interactionVector);
                    if (distanceToInteraction < 3) {
                        for (let i = 0; i < 3; i++) {
                            if (virtualCopies.length < maxVirtualCopies) {
                                const targetIndex = Math.floor(Math.random() * objects.length);
                                const targetPos = objects[targetIndex].position.clone();
                                
                                const virtualCopy = createVirtualCopy(obj, targetPos);
                                virtualCopies.push(virtualCopy);
                            }
                        }
                        
                        obj.material.emissiveIntensity = 1.5;
                        setTimeout(() => {
                            obj.material.emissiveIntensity = 0.7;
                        }, 300);
                    }
                });
            }
        }

        document.addEventListener('mousemove', onMouseMove, { passive: true });
        document.addEventListener('touchmove', onTouchMove, { passive: true });
        document.addEventListener('mouseup', onInteractionEnd, { passive: true });
        document.addEventListener('touchend', onInteractionEnd, { passive: true });
        document.addEventListener('click', onClick, { passive: true });
        document.addEventListener('touchstart', onTouchStart, { passive: true });

        window.addEventListener('resize', onWindowResize, false);

        function onWindowResize() {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        }

        animate();
    </script>
</body>
</html>
