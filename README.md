# Macy-Baer.github.io
first repository for pages

## Project title
##Biogeography course final project site
-work description
- 
#Download & install all necessary packages

install.packages (c("knitr","rmarkdown","dplyr","plyr","ggplot2","sf","tidyverse","rnaturalearth","rnaturalearthdata","classInt","gridExtra", "devtools"))

library(knitr)
library(rmarkdown)
library(dplyr)
library(plyr)
library(ggplot2)
library(sf)
library(tidyverse)
library(devtools)
devtools :: install_github("ropensci/rnaturalearthhires")
library(rnaturalearth)
library(rnaturalearthdata)
library(classInt)
library(gridExtra)

#Read FIA database 
tree <- readRDS("U:/Biogeo/FIA_tree_master1.RDS")

#Filter needed species
oak <- tree %>%
  filter(GENUS == "Quercus")

#Create distribution figures for individual species with rnaturalearth
oakspecies <- oak %>%
  filter(COMMON_NAME == "white oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "white oak") +
      labs(title = "Distribution of white oak", x = "Longitude", y = "Latitude")
      
![image](https://github.com/user-attachments/assets/0c0b036a-689f-4a16-b456-73b3727d31e5)

![image](https://github.com/user-attachments/assets/7598cd93-44b7-4e58-a7b5-02aeb113bb7e)

![image](https://github.com/user-attachments/assets/d9a812cc-b109-4d8f-a612-45fb07e596d8)

![image](https://github.com/user-attachments/assets/65ba6f84-2db7-49ba-91bf-ff5853488ea8)

![image](https://github.com/user-attachments/assets/266fe95d-546f-4737-b51b-ce601a2b5e58)

![image](https://github.com/user-attachments/assets/b073a8f2-98f4-4854-bf78-5477bf9371fb)

