Scripts to generate charts
==========================

Scripts require:

    gnuplot bpftrace wireshark

The magic is contained in the `tcp.bt` bpftrace script. You probably
need pretty fresh bpftrace with `kprobe` support compiled in.

The charts are generated by running a python `window.py` script inside
network namespace, configured with high latency with `tc-netem`.

First, set up a network namespace:

    sudo bash ns_cleanup.sh; sudo bash ns_setup.sh

Then to generate the chart run:

    sudo bash run.sh; xdg-open out.png

See the `run.sh` script for the configuration details.
