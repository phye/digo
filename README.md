# digo

## Why?
It's been widely spreaded that it's very easy to write an HTTP server in Golang that is C10K suitable, without any complex async/callback
logics that's both error prone and difficult to understand. How's that possible?

What's the internal of the *magic* channel in go? How's it different from traditional sync mechanisms like mutex/semaphore .etc? 

Heard many times that a golang process can more than 1k goroutines running. If goroutine is /implemented as/ thread, how can that be
efficient? If it's not internally a thread, what is indeed a goroutine?

Most of the answers to the questions above are hidden in golang std libraries. By reading and taking notes of the go std code, hopefully I
can answer the questions above more accurately. Also, by learning golang std code, I can also learn the skills from the top golang
professors, *for free*!

## Notes of OrgMode
I've been personally using OrgMode for more than two years, and is still inspired/pleased by the powerful features of OrgMode. Then one day,
I came to realize that I can store link to Golang source code easily in OrgMode! And you can also jump code easily with go mode and gocode
easily. 

Bravo! 
