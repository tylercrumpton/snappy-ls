# snappy-ls
Synapse Wireless SNAPpy libraries/scripts for the LightSense.

# Overview
The `lightsense.py` SNAPpy script will turn your LightSense into
a low-power-consumption motion-triggered wireless sensor. On the
detection of motion, the LightSense will send an ls_report immediately,
and every few seconds while motion is still occurring. When the
LightSense detects stillness, it will report every few minutes. The
report will look like:

    ls_report(<script_version>, <battery>, <photo>, <temp>, <motion>)
    
| Value             | Description                             | Example             |
| ----------------- | --------------------------------------- | ------------------- |
| \<script_version> | Major.Minor.Patch script version string | "v1.0.0"            |
| \<battery>        | Battery voltage (mV)                    | 2966                |
| \<photo>          | Photocell averaged reading              | 54                  |
| \<temp>           | Temperature averaged reading            | 253                 |
| \<motion>         | Motion event string                     | "motion" or "still" |

# Build the script!
In order to build the script, you'll first need tox installed:

    pip install tox
    
Then, run the tox build target:

    tox -e build
    
This will create the `lightsense.spy` file that you can upload to
a LightSense running 2.4.25 SNAP firmware.
