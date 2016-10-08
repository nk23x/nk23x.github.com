---
published: true
title: readability.com exports
layout: post
---
readability.com closes down and here is what i did: 

* generated and downloaded the json export data at readability
* pulled all urls out of the file 
* resubmitted everything to http://archive.is

~~~~~~
    for f in $(cat READABILITY.txt); do 
      wget -q -O - http://archive.is/submit/ \
         --post-data="url=$(echo "$f" \
            | perl -pe 's/([^A-Za-z0-9])/sprintf("%%%02X", ord($1))/seg;')" \
      | grep 'var shortlink' ; 
    done
~~~~~~
what i got is a bunch of shortlinks which i submitted to 

* http://tools.buzzstream.com/meta-tag-extractor

and recieved a nice csv file containing the relevant metadata for each shortlink.

it's just quick and dirty but it works fine for me.