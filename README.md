**_BoxControlled.html_** uses an ill-advised implementation of _THREE.BoxGeometry(x,y,z)_ from _three.js_ to simulate a 3D (perspective) box that moves both automatically and in response to dragging the mouse. &nbsp;This method is inefficient because it repeatedly creates and destroys the structure. &nbsp;_THREE.EdgesGeometry(geometry,thresholdAngle)_ is used to specify the appearance of the box's outer edges. &nbsp;Additionally, there is automatic movement of the box across the screen, while manual 'orbit' controls with the mouse are provided by _OrbitControls.js_.

**_MeshTranslate.html_** is a preferred way to render the box because the structure is not repeatedly created and destroyed. &nbsp;This is because _THREE.Mesh(geometry,material)_ is a subclass of _THREE.Object3D_, so we can use the inherited 'translate' methods.


Note: Full versions of _OrbitControls.js_ and _three.js_ are provided for reference/educational purposes. &nbsp;The authors of _OrbitControls.js_ are specified at the top of that file.
