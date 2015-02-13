R presentation
========================================================
author: Juan Esteban Restrepo
date: 

Body Mass Index
========================================================
For this presentation, I want to show a simple code for calculating the body mass index of a certain individual. For this simple calculation, we will take into account four things:

- The individual's weight in kilograms.
- The individual's height in meters.
- If an individual's weight is not in kilograms, the individual's weight must be converted to 
  kilograms.
- If an individual's height is not in meters, the individual's height must be converted to
  meters.
  
  The next slide covers exhibits the server.R file for calculating Body Mass Index:

server.R
=================================================================================================


```r
library(shiny)
bodymassindex<-function(weight,height) weight/((height)^2)
shinyServer(function(input,output){
output$inputValue1<-renderPrint(
{input$weight});output$inputValue2<-
renderPrint({input$height});
output$prediction<-
renderPrint({bodymassindex(input$weight,
input$height)})})
```

Description of server
=================================================================================================

The bodymassindex function takes two arguments. The first argument is weight, and the second argument is height(in kilograms and meters, respectively). Then, it divides the weight by the square of the height. 

Once this function is defined, the server prints individual's inputs of weight and height. Finally, the server calculates the body mass index from the individual's inputs and prints the result.

References
=================================================================================================
Clicking on the link below lets you go my ui.R code and server.R code. 
[ui.R and server.R]("https://github.com/JUANESTEBAN/datasciencecoursera/tree/master/shinyapps",
  "ui.R and server.R codes")
Clicking on this other link below lets you go to the shiny application.
[Shiny application]("https://juanestebanrestrepo.shinyapps.io/shinyapps")
