# moonphases
![documentation](https://user-images.githubusercontent.com/116059680/230787107-20bf9ab5-763f-46cc-9af7-8f6b5ce41ffa.png)

This code is a TradingView script that uses the Pine programming language to plot the moon phases on the price chart based on UTC time. 
It uses the built-in ta.moonphase() function to get the moon phase data and the plotchar() function to draw the symbols. 
The indicator can be used for visualizing the lunar cycles and their possible effects on the market

Here is an explanation of each line of the code:
//@version=5 // This line specifies the version of Pine Script to use. Version 5 is the latest and most advanced version.
indicator("Moon Phases Strategy", overlay=true) // This line defines the indicator's name and settings. The overlay argument sets the indicator to be plotted on the main chart instead of a separate pane.
// Get the moon phase data from the built-in indicator 
moonPhase = ta.moonphase(time(timeframe.period, "UTC")) // This line assigns the variable moonPhase to the value returned by the ta.moonphase() function. This function returns an integer from 0 to 7 representing the current moon phase. The time argument converts the current bar's time to UTC time using the time() and timeframe.period functions.
// Plot the moon phases as circles 
plotchar(moonPhase == 0, "New Moon", "●", location.abovebar, color.new, size = size.huge) // This line plots a black circle above the bar when the moonPhase variable is equal to 0, which means a new moon. The plotchar() function takes six arguments: a condition, a label, a symbol, a location, a color and a size. The label and symbol arguments can be any string, but some symbols are predefined in Pine Script such as "●".
plotchar(moonPhase == 1, "Full Moon", "●", location.abovebar, color.white, size = size.huge) // This line plots a white circle above the bar when the moonPhase variable is equal to 1, which means a full moon. The color argument can be any predefined color in Pine Script such as color.white.
// Plot the moon phases as half circles 
plotchar(moonPhase == 2, "Waxing Crescent", "◐", location.abovebar, color.green, size = size.huge) // This line plots a green half circle above the bar when the moonPhase variable is equal to 2, which means a waxing crescent. The symbol argument can be any Unicode character such as "◐".
plotchar(moonPhase == 3, "Waning Crescent", "◑", location.abovebar, color.red, size = size.huge) // This line plots a red half circle above the bar when the moonPhase variable is equal to 3, which means a waning crescent. The symbol argument can be any Unicode character such as "◑".
plotchar(moonPhase == 4, "First Quarter", "◓", location.abovebar, color.green, size = size.huge) // This line plots a green half circle above the bar when the moonPhase variable is equal to 4, which means a first quarter. The symbol argument can be any Unicode character such as "◓".
plotchar(moonPhase == 5, "Third Quarter", "◒", location.abovebar, color.red, size = size.huge) // This line plots a red half circle above the bar when the moonPhase variable is equal to 5, which means a third quarter. The symbol argument can be any Unicode character such as "◒".
// Plot the moon phases as curved lines 
plotchar(moonPhase == 6, "Waxing Gibbous", ")", location.abovebar, color.green, size = size.huge) // This line plots a green curved line above the bar when the moonPhase variable is equal to 6, which means a waxing gibbous. The symbol argument can be any ASCII character such as ")".
plotchar(moonPhase == 7, "Waning Gibbous", "(", location.abovebar, color.red, size = size.huge) // This line plots a red curved line above the bar when the moonPhase variable is equal to 7, which means a waning gibbous. The symbol argument can be any ASCII character such as "(".

To create this indicator in TradingView, you need to follow these steps:
1. Open the TradingView website and log in to your account.
2. On the top left corner, click on the "Chart" tab to open a new chart.
3. On the bottom panel, click on the "Pine Editor" tab to open the code editor.
4. Copy and paste the code into the editor and click on the "Add to Chart" button on the top right corner.
5. The indicator will be added to your chart and you can see the moon phases plotted on it.

