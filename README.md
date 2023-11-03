# radial-gyre
Compute radial mode frequencies with GYRE and put them in MESA history output. 

The "magic" happens in `src/run_star_extras.f90`, which calls GYRE with the supplied `gyre.in` inlist to compute radial modes, and then stores them in the `LOGS/history.data` output. 

It only happens if the `&control` parameter `x_logical_ctrl(1) = .true.` is set, as in the provided inlist. 

You may need to adjust some things in the GYRE inlist to your needs, such as the frequency scan range or the numerical scheme, but probably it's plug-and-play for most applications. 
