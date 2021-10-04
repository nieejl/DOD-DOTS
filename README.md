# DOD-DOTS
This repo is a compilation of material for data-oriented design and Unity DOTS.

DOTS is the Data-Oriented Technology Stack for the Unity game engine. DOTS builds on a component-based storage model using the Arrays of Structures pattern, in order to provide massive performance gains when compared to an object-oriented storage model.

Mike Acton has several inspirational and relevant talks on data-oriented design. There will be some overlap between the videos listed, but each contains unique information.

For an introduction to data-oriented design I recommend first watching 2 talks by Mike Acton:
CppCon 2014: Mike Acton "Data-Oriented Design and C++"
https://www.youtube.com/watch?v=rX0ItVEVjHc
The slides are found here: 
https://github.com/CppCon/CppCon2014/raw/master/Presentations/Data-Oriented%20Design%20and%20C%2B%2B/Data-Oriented%20Design%20and%20C%2B%2B%20-%20Mike%20Acton%20-%20CppCon%202014.pptx

I suggest following that up with "Solving the Right Problems for Engine Programmers - Mike Acton‌ (TGC 2017)"
https://www.youtube.com/watch?v=4B00hV3wmMY

At this point it probably makes sense to get a quick overview of how Unity works, by reading some of the manual. I would probably start here: https://docs.unity3d.com/Manual/ScriptingSection.html , and follow that up with https://docs.unity3d.com/Packages/com.unity.entities@latest/.

Then I would recommend watching this talk about DOTS and the intent behind some of the features: "Building a Data-Oriented Future - Mike Acton"
https://www.youtube.com/watch?v=u8B3j8rqYMw

The previously mentioned material should have given a sufficient background. There are a few choices to make for the future direction. If the direction is focused around database layouts, 'Weaving Relations for Cache Performance', by Anastassia Ailamaki et al. from the VLDB conference in 2001 is a great read.

It makes sense to consider how game workloads are typically not very much like OLTP workloads. Typically there is a need for examining much more data, but a lower amount of times (usually capped by the monitor / gpu capabilities). However, because there is a need to examine lots of data, the hardware can be utilized very well, by using vector operations and out of order execution to our advantage.

I really recommend watching this video, to get a bit more insight into microarchitecture: https://youtu.be/rglmJ6Xyj1c
This is well paired with the TMAM cookbook from intel: https://software.intel.com/content/www/us/en/develop/documentation/vtune-cookbook/top/methodologies/top-down-microarchitecture-analysis-method.html
The user guide is also going to be very useful when diving into profiling: https://software.intel.com/content/www/us/en/develop/documentation/vtune-help/top.html

How all that ties into game programming can to some extent be explained by having a look at the (somewhat dated, but still relevant) dodbook: https://www.dataorienteddesign.com/dodbook/

There are a number of projects on DOTS performance that give good insight into how it is used, and what kind of performance it can deliver.
This first one is an intel / unity project, showcasing performance differences.
https://software.intel.com/content/www/us/en/develop/articles/get-started-with-the-unity-entity-component-system-ecs-c-sharp-job-system-and-burst-compiler.html

