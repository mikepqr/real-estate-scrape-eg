# real-estate-scrape example

A repository demonstrating the use of
[real-estate-scrape](https://github.com/mikepqr/real-estate-scrape) to store the
estimated value of a property on Redfin and Zillow every night using Github
Actions.

(A paid scraperapi key is required to scrape Zillow. This example repository
does not have access to a paid key, so you'll only see data from Redfin below.)

![Plot of Redfin and Zillow valuation as a function of time](data.png)

See [`data.csv`](data.csv) and [`data.png`](data.png) (above) for example output
for [71 Beverly Park, Beverly
Hills](https://www.redfin.com/CA/Beverly-Hills/71-Beverly-Park-90210/home/22740038)
(not my house!)

## Automated usage

1. Sign up for [scraperapi](https://www.scraperapi.com/) and make a note of your
   API key. The free account is enough to get started scraping Redfin. A paid
   scraperapi account is required to successfully scrape Zillow.

2. Make a copy of this repository, e.g. [using the
   template](https://github.com/mikepqr/real-estate-scrape-eg/generate).

3. Commit changes deleting `data.csv` and `data.png`.

4. Under Settings > Secrets, configure environment variables containing the URLs
   of the address on Redfin and Zillow and your scraperapi key:
    - `REDFIN_URL`, e.g.
      `https://www.redfin.com/CA/Beverly-Hills/71-Beverly-Park-90210/home/22740038`
    - `ZILLOW_URL`, e.g.
      `https://www.zillow.com/homedetails/71-Beverly-Park-Beverly-Hills-CA-90210/2064298430_zpid/`
    - `SCRAPERAPI_KEY`, e.g.`abcdefqwert12345`

The scraping job runs every day at 5am UTC. Come back in 24 hours and you should
find `data.csv` in your repository. Come back a few days later and you should
see the beginnings of a chart in `data.png`.

Alternatively, you can run the scraping job manually as often as you like by
clicking "Run workflow" under Actions > scrape on GitHub.

## Advanced/manual usage

See [real-estate-scrape](https://github.com/mikepqr/real-estate-scrape).
