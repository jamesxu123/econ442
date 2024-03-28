# Scraping ARWU process

1. I noticed that ARWU uses the Nuxt web framework
2. I dig around the files and find a `payload.json` which contains minified version of code that contains the actual rankings
3. The data is wrapped around a function closure where I catch the return result
4. I parse this return result into a data set