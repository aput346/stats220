# Welcome to my Github Website :)

## About me
I am a second year Data Science student and I am Indonesian.

## My Meme
My meme is just a simple joke inspired from the game of Valorant and I made it using the R package [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).

![my_meme](https://user-images.githubusercontent.com/100745310/158976770-1784a090-6f95-40dd-a4e6-06c2ae3a470d.png)

## Meme explanation
My current favourite game is Valorant and so I used it as inspiration for my meme. The pictures I used is one of the most popular characters in the game, Jett.
The first row depicts a sad Jett, corresponding to the text which just simply means that your gaming partner/duo is at the bottom of the leaderboard.
The second row depicts a happy Jett, corresponding to the text which simply means that your gaming partner/duo is instead at the very top of the leaderboard.

## R code
Below is the R code I used to create this meme.

``r

happy_jett <- image_read("https://i.pinimg.com/originals/27/73/ee/2773eec3599f861615a47688a9762ee7.png") %>%
  image_scale(500)

sad_jett <- image_read("https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/6297aec8-0582-4204-bd60-a34bae51535d/de12b5e-5408cfad-8758-4f71-b1ab-7a2f785ebee8.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzYyOTdhZWM4LTA1ODItNDIwNC1iZDYwLWEzNGJhZTUxNTM1ZFwvZGUxMmI1ZS01NDA4Y2ZhZC04NzU4LTRmNzEtYjFhYi03YTJmNzg1ZWJlZTguanBnIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.Ie0YrszUdLRv4hV5FRJYTNX_wsNmF4C0u6-LGemuaKA") %>%
  image_scale(500)

top_frag_text <- image_blank(width = 500,
                             height = 721,
                             color = "#FF0000") %>%
  image_annotate(text = "When your duo\ntop frags :D",
                 color = "#000000",
                 size = 50,
                 font = "Impact",
                 gravity = "center")

bottom_frag_text <- image_blank(width = 500,
                                height = 500,
                                color = "#FF0000") %>%
  image_annotate(text = "When your duo\nbottom frags D:",
                 color = "#000000",
                 size = 50,
                 font = "Impact",
                 gravity = "center")

first_row <- c(sad_jett, bottom_frag_text) %>%
  image_append()

last_row <- c(happy_jett, top_frag_text) %>%
  image_append()

meme <- c(first_row, last_row) %>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")

```
