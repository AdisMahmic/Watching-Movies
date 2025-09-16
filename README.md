
<img src="https://github.com/user-attachments/assets/32083e83-2492-465e-b97c-b554029c7659" alt="Movies_end_of_year_2017" width="800">

# Watching-Movies
Ever wondered how movies from different eras compare to eachother in terms of sales and reviews? Ever had the age old question of whether marvel or DC is better? Well now with the watching movies repository, All of your questions can finally be answered and more!

## About Dataset
The Movie Database (TMDb) is an extensive resource that offers detailed information on films, including titles, ratings, release dates, revenues, genres, and more. This dataset includes a collection of 1,000,000 movies sourced from TMDb.

## Goals
1. Determine whether Marvel or DC movies are more sucessful. Not only in the present, but also in the past decades.
2. Compare different Genre's and see which one has thr highest ratings, revenue, ect..
3. Calculate the difference between budget and revenue to see wich movies made the most money with the least amount of budget.

## File Contents
The movies database contains a variety of different columns such as Title, Average Vote, Vote Count, Status, Release Date, Revenue, Runtime, and various other attributes.

## Git Bash commands performed on the dataset to extract data:

### Part 1:
Here I used pwd to show which directory I am in:
```
amahm@AdisSurface MINGW64 ~ (master)
$ pwd
/c/Users/amahm
```
### Part 2:
In order to store all my files in to a single location. I used the mkdir command to create a directory for all of my project files.
```
amahm@AdisSurface MINGW64 ~/downloads (master)
$ mkdir ITEC4220

amahm@AdisSurface MINGW64 ~/downloads (master)
$ ls
'ITEC3700 CMS Interview Notes (1).doc'
** ITEC4220/**
```
### Part 3:
With my new directory ITEC4220 created, I then use the cp command to copy the movies dataset into my directory.
```
amahm@AdisSurface MINGW64 ~/downloads (master)
$ cp "movies dataset.csv" ITEC4220
```
### Part 4:
I then cd into my new directory, and use the ls command to list everything inside of my current directory. I then used the head command to show the first 10 records inside my dataset.
```
amahm@AdisSurface MINGW64 ~/downloads (master)
$ cd ITEC4220

amahm@AdisSurface MINGW64 ~/downloads/ITEC4220 (master)
$ ls
'movies dataset.csv'

$ head 'movies dataset.csv'
"id","title","vote_average","vote_count","status","release_date","revenue","run

amahm@AdisSurface MINGW64 ~/downloads/ITEC4220 (master)
$ pwd
/c/Users/amahm/downloads/ITEC4220
```
### Part 5: 
To further analyze my dataset, I used the head -1000 command to show the first 1000 records.
```
amahm@AdisSurface MINGW64 ~/downloads/ITEC4220 (master)
$ head -1000 'movies dataset.csv' > '1000movies.csv'
Action, Crime, Thriller","Super Cool ManChu, Miramax, A Band Apart","United Sta
```
### Part 6: 
Using the grep command, I displayed every record that contained the word "Horror".
```
amahm@AdisSurface MINGW64 ~/downloads/ITEC4220 (master)
$ grep "Horror" 1000movies.csv
"346364","It","7.242","18018","Released","2017-09-06","701800000","135","False","/tcheoA2nPATCm2vvXw2hVQoaEFD.jpg","40000000","http://itthemovie.com/","tt1396484","en","It","In a small town in Maine, seven children known as The Losers Club come face to face with life problems, bullies and a monster that takes the shape of a clown called Pennywise.","Horror,
```
### Part 7:
For the final part, I used grep to find every movie inside the database that starts with the word "The".
```
amahm@AdisSurface MINGW64 ~/downloads/ITEC4220 (master)
$ grep -E '^"[^"]+","The' "movies dataset.csv" > filtered1.csv
```
-E = extended grep.
^"  =  start of the line must start with ". I did this because when I run head I noticed 
"[^"]+" =  start of the line must start with ". I did this because when I run head I noticed that each column title is surrounded by quotation marks.
,"The = matches the comma, then a ", then the word The at the start of the title column.
"movies dataset.csv" > filtered1.csv = writing grep command into new .csv file called filtered1.csv.
### Part 7.2:
I then used the sed command to replace the word "The" with 3 astrix instead.
```
amahm@AdisSurface MINGW64 ~/downloads/ITEC4220 (master)
$ sed -E 's/^("[^"]+"),"The/\1,"***/' filtered1.csv > final.csv
```
## R-Markdown HTML File
To gain hands-on experience with R, I created an R Markdown file in RStudio and experimented with basic commands such as generating histograms and running t-tests.
[R-Markdown HTML](https://rpubs.com/Adis_M2003/1340175)
## JSON File of Dataset:

[movies dataset JSON](Movies-Dataset-JSON.json)





