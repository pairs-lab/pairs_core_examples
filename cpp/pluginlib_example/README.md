# Pluginlib Example

A working example showcasing the [pluginlib](http://wiki.ros.org/pluginlib) feature of ROS, simular to what is used between the [ControlManager](https://github.com/pairs-lab/pairs_uav_managers#controlmanager) and the [trackers](https://github.com/pairs-lab/pairs_uav_trackers#mrs-uav-trackers-) and [controllers](https://github.com/pairs-lab/pairs_uav_controllers#mrs-uav-controllers-) within the [PAIRS UAV System](https://github.com/pairs-lab/pairs_uav_system).

## pairs_example_plugin_manager package

* defines the [interface](https://github.com/ctu-mrs/example_ros_pluginlib/blob/master/pairs_example_plugin_manager/include/pairs_example_plugin_manager/plugin_interface.h) for plugins
* defines a [common handlers](https://github.com/ctu-mrs/example_ros_pluginlib/blob/master/pairs_example_plugin_manager/include/pairs_example_plugin_manager/common_handlers.h), which are passed to the plugins
* dynamically loads the plugins defined in [plugins.yaml](https://github.com/ctu-mrs/example_ros_pluginlib/blob/master/pairs_example_plugin_manager/config/plugins.yaml) and [pairs_example_plugin_manager.yaml](https://github.com/ctu-mrs/example_ros_pluginlib/blob/master/pairs_example_plugin_manager/config/pairs_example_plugin_manager.yaml)
* activates the plugin defined in [pairs_example_plugin_manager.yaml](https://github.com/ctu-mrs/example_ros_pluginlib/blob/master/pairs_example_plugin_manager/config/pairs_example_plugin_manager.yaml)
* regularly updates the active plugin and queries a result

## pairs_example_plugins package

* defines a plugin complying with the [interface](https://github.com/ctu-mrs/example_ros_pluginlib/blob/master/pairs_example_plugin_manager/include/pairs_example_plugin_manager/plugin_interface.h)
* the plugin loads its params and prepares itself for activation
* it calculates results in its `update()` method and returns them to the manager

# How to start it?

```bash
roslaunch pairs_example_plugin_manager pairs_example_plugin_manager.launch
```

# Dependencies

* [pairs_lib](https://github.com/pairs-lab/pairs_lib) for param loading and mutexing
