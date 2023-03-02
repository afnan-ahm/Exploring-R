# Exploring-R

#Data Analysis through R
data("ToothGrowth")
View(ToothGrowth)
install.packages("dplyr")
#filter
filtered_tg <- filter(ToothGrowth,dose==0.5)
View(filtered_tg)
#sort
arrange(filtered_tg,len)
#Nested function
arrange(filter(ToothGrowth,dose==0.5),len)
#pipe
filtered_toothgrowth <- ToothGrowth %>%
  filter(dose==0.5) %>%
  group_by(supp) %>%
  arrange(len)
##
filtered_toothgrowth <- ToothGrowth %>%
  filter(dose==0.5) %>%
  group_by(supp) %>%
  summarize(mean_len = mean(len,na.rm = T),.group="drop")
