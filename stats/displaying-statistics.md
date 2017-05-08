# Displaying statistics

In this chapter, the focus is on adding several tabs with charts that display realtime aggregated stats about our tweet stream.

It is important to note that this sample and server are only doing simple aggregation calculations, such as averages and counts. This is not a course in statistics or data analysis, but a demonstration of how to consume metrics that are provided in realtime.

All of the data has been formatted on the backend for easy consumption in the frontend. Sometimes you have to do data wrangling in Angular, but I prefer to send the data to Angular in the format it needs to minimize overhead, unless there is a strong reason not to.