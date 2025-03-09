This was a bit tough to figure out so here is a simple process to get a 3d model into gazebo simulation. We will do a 3D model of a ArUco marker.

1. Get a PNG image of the desired ArUco marker.
2. Open blender
3. Add an image mesh plane: `Shift+A -> Image -> Mesh Plane`
4. Go to scripting tab
5. Paste python script from [this repo](https://github.com/sebdeveloper6952/gazebo_sdf_exporter/tree/master)
6. Run script
7. Choose place to save model, it must be in a directory that Gazebo can find (`GZ_SIM_RESOURCE_PATH`)
8. Edit your gazebo file to include model (launch, world file)
9. Verify it is able to load file
10. If you need massless (static) objects in gazebo you will need to modify the `model.sdf` file. Add a `<static>true</static>` element inside `<model>` and a `<mass>0</mass>` inside every `<link>` element.