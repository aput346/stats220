# Welcome to my Github Website :)

## About me
I am a third year Data Science student. I take STATS220 as it is a requirement for my degree :D

## My Meme
My meme is just a simple joke inspired from the game of Valorant and I made it using the R package [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).

![my_meme](https://user-images.githubusercontent.com/100745310/224592950-15070ac9-3cee-4ed5-95e1-77a2f08bff5b.png)

## Meme explanation
My current favourite game is Valorant and just like Anna I also love cats so I used both of those interests as inspiration for my meme. The pictures I used are just of some cats I found online.
1. The first row depicts a happy cat, corresponding to the text in which I win my valorant game.
2. The second row depicts a sad cat, corresponding to the text in which I lose my valorant game.

## R code
Below is the R code I used to create this meme.

~~~r
happy_cat <- image_read("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSGleZA5JaGyQazY6m3qokImDux2EAYJhyVhw&usqp=CAU") %>%
  image_scale(500)

sad_cat <- image_read("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSSKm2Z4ECXF6YXyDkV-2jlAr2QD8umyNsvNQ&usqp=CAU") %>%
  image_scale(500)

happy_cat_text <- image_blank(width = 500,
                             height = 422,
                             color = "#000000") %>%
  image_annotate(text = "When I win my\nvalorant game :D",
                 color = "#FFFFFF",
                 size = 50,
                 font = "Impact",
                 gravity = "center")

sad_cat_text <- image_blank(width = 500,
                                height = 333,
                                color = "#000000") %>%
  image_annotate(text = "When I lose my\nvalorant game D:",
                 color = "#FFFFFF",
                 size = 50,
                 font = "Impact",
                 gravity = "center")

first_row <- c(happy_cat, happy_cat_text) %>%
  image_append()

last_row <- c(sad_cat, sad_cat_text) %>%
  image_append()

meme <- c(first_row, last_row) %>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")

~~~
