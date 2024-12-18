# Macy-Baer.github.io
first repository 

## Mapping Oak Distribution: Spatial Patterns and Phylogenetic Links
##Biogeography course final project site
-

##Introduction:
-
-I chose these species because oak trees have a long evolutionary history. This ensures a large number of species to observe, and improves the chance that significant spatial patterns will emerge.

-The objective of my project is to show the distribution of various oak species in the FIA database and compare their placement in the eastern United States. The species shown were chosen due to their genetic/phylogenetic grouping defined in Hipp et al

##Hipp et al:
- 
-Gene flow, species migration, & evolutionary history of oaks

-Objective: phylogenomic sampling with Quercus robur genome to define lineages

-Methods (specifically for phylogenetic analysis): Maximum likelihood (ML) analysis in RAxML, then used to create an all-tips tree which grouped all 246 observed Quercus species

##Data:
-
-I chose species that were within the same grouping on the Figure 1 all-tips tree (Hipp et al.), and native to the eastern United States.

-FIA database

##Methods:
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



#example species to test code: white oak
![image](https://github.com/user-attachments/assets/0c0b036a-689f-4a16-b456-73b3727d31e5)


#change each species (common name) in code to map them out
#choose group from Fig 1 (Hipp et al., then map the distriutions of species within each group)

#Group: Prinoids
-
oakspecies <- oak %>%
  filter(COMMON_NAME == "bur oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "bur oak") +
      labs(title = "Distribution of bur oak", x = "Longitude", y = "Latitude")
      
![image](https://github.com/user-attachments/assets/7598cd93-44b7-4e58-a7b5-02aeb113bb7e)

oakspecies <- oak %>%
  filter(COMMON_NAME == "overcup oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "overcup oak") +
      labs(title = "Distribution of overcup oak", x = "Longitude", y = "Latitude")

![image](https://github.com/user-attachments/assets/d9a812cc-b109-4d8f-a612-45fb07e596d8)

#Group: Albae
-
oakspecies <- oak %>%
  filter(COMMON_NAME == "swamp white oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "swamp white oak") +
      labs(title = "Distribution of swamp white oak", x = "Longitude", y = "Latitude")

![image](https://github.com/user-attachments/assets/65ba6f84-2db7-49ba-91bf-ff5853488ea8)

oakspecies <- oak %>%
  filter(COMMON_NAME == "chestnut oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "chestnut oak") +
      labs(title = "Distribution of chestnut oak", x = "Longitude", y = "Latitude")

![image](https://github.com/user-attachments/assets/266fe95d-546f-4737-b51b-ce601a2b5e58)

oakspecies <- oak %>%
  filter(COMMON_NAME == "swamp chestnut oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "swamp chestnut oak") +
      labs(title = "Distribution of swamp chestnut oak", x = "Longitude", y = "Latitude")
      
![image](https://github.com/user-attachments/assets/b073a8f2-98f4-4854-bf78-5477bf9371fb)

Group: Stellatae
-
oakspecies <- oak %>%
  filter(COMMON_NAME == "post oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "post oak") +
      labs(title = "Distribution of post oak", x = "Longitude", y = "Latitude")

![image](https://github.com/user-attachments/assets/bc1fc780-3249-40c8-ae37-95cbfb7b3729)

oakspecies <- oak %>%
  filter(COMMON_NAME == "dwarf post oak") 

usa <- ne_states(country = "United States of America", returnclass = "sf")
usa31 <- usa %>%
  filter(longitude >=-95 & longitude <= -65)

ggplot() +
   geom_sf(data = usa31, fill = "lightblue", color = "grey50")+
  geom_point(data= oakspecies, aes(x= LON, y= LAT), size = 0.5) +
       scale_color_gradient(low = "grey90", high = "grey10", name = "dwarf post oak") +
      labs(title = "Distribution of dwarf post oak", x = "Longitude", y = "Latitude")

![image](https://github.com/user-attachments/assets/c04c1507-d8b3-4dc1-8bee-a512b971a594)

##Results
-
Group: Prinoids

-the bur oak and overcup oak did not show any spatial similarities, overlap, or discernable patterns


Group: Albae

-These species showed a migration southward

-the swamp white oak and swamp chestnut oak showed sparse distributions, while the chestnut oak (central) was condensed


Group: Stellatae

-the post oak was abundant, and the dwarf post oak was scarse

-these two species showed a possible eastern migration


##Citations:
-

Hipp, Andrew L., et al. “Genomic landscape of the Global Oak Phylogeny.” New Phytologist, vol. 226, no. 4, 14 Oct. 2019, pp. 1198–1212, https://doi.org/10.1111/nph.16162. 

FIA database


