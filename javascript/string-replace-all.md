javascript string.replace only replaces first occurence and is misleading.  
to replace all occurences it must be written like : `str = str.replace(new RegExp('replacethis','g'),'withthis');`
