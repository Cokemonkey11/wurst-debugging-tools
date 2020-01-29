Provides two packages:

# import WurstProfile

- Instrument code hot-spots by calling `profile()` inline
- Display the top 5 hot-spots by calling `Profile.display(player toWho)`

```wurst
import ClosureTimers

import WurstProfile


init
    doPeriodically(1.) ->
        profile()

    doPeriodically(ANIMATION_PERIOD) ->
        profile(10)
        for i = 0 to 9
            // Shuffle the kurmudgeons.

    doAfter(7.) ->
        Profile.display(localPlayer)
```


# import WurstAllocationHistogram

- Display the top-10 class allocations by max-instance-count, using `reflection_summary(player displayTo)`

```wurst
import Reference

import WurstAllocationHistogram


init
    for i = 0 to 9
        new Reference<real>(1.)
        for i = 7 to 66
            let q = new Reference<int>(i)
            if q % 3 == 0
                destroy q

    reflection_summary(localPlayer)
```
