# PAIRS Core Examples

A collection of small, self-contained example packages that show how to write your own code against the [PAIRS UAV System](https://github.com/pairs-lab/pairs_uav_system). Each example is a minimal, working ROS package you can copy and adapt: simple ROS nodelets, controller and tracker plugins for the control stack, a pluginlib walkthrough, and a Python path generator. They are meant as starting points and reference material rather than production flight code.

## Contents

C++ examples:

* **pairs_example_waypoint_flier_simple** (`cpp/waypoint_flier_simple`) — minimalistic C++ nodelet using plain ROS features, flying a UAV through a list of waypoints.
* **pairs_example_waypoint_flier** (`cpp/waypoint_flier`) — fuller C++ nodelet that uses PAIRS libraries and wrappers, with dynamic reconfigure and waypoint-following services.
* **pairs_example_controller_plugin** (`cpp/controller_plugin`) — example Controller plugin loaded by the PAIRS control manager (a simple PID controller).
* **pairs_example_tracker_plugin** (`cpp/tracker_plugin`) — example Tracker plugin loaded by the PAIRS control manager.
* **pairs_example_plugin_manager** / **pairs_example_plugins** (`cpp/pluginlib_example`) — standalone pluginlib demonstration showing how a manager nodelet loads runtime plugins, mirroring the pattern used by the control manager.

Python example:

* **pairs_example_sweeping_generator** (`python/sweeping_generator`) — minimal Python node that generates a sweeping (boustrophedon) coverage path and sends it to the UAV.

Each package ships its own `launch/` file and a plain-tmux `tmux/` session that brings up the simulator, control stack, and the example together.

## Install (ROS 1 Noetic)

The examples are published as individual packages, for example:

```bash
sudo apt install ros-noetic-pairs-example-waypoint-flier
sudo apt install ros-noetic-pairs-example-waypoint-flier-simple
sudo apt install ros-noetic-pairs-example-controller-plugin
sudo apt install ros-noetic-pairs-example-tracker-plugin
sudo apt install ros-noetic-pairs-example-plugin-manager
sudo apt install ros-noetic-pairs-example-plugins
sudo apt install ros-noetic-pairs-example-sweeping-generator
```

## Usage

Launch an individual example node:

```bash
roslaunch pairs_example_waypoint_flier example_waypoint_flier.launch
roslaunch pairs_example_waypoint_flier_simple waypoint_flier_simple.launch
roslaunch pairs_example_sweeping_generator sweeping_generator.launch
roslaunch pairs_example_plugin_manager example_plugin_manager.launch
```

Or run a complete simulation-plus-example demo from its tmux session, e.g.:

```bash
cd cpp/waypoint_flier/tmux
./start.sh   # ./kill.sh to stop
```

# Disclaimer

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
