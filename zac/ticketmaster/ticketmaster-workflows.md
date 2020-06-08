# Functional System Design

## Workflow for buying a ticket
- Search for event, artist, or venue.
    **get_events(location, quantity, api_key, category, date_range)**

- As you are typing, 5 links of each category is displayed and updated as you continue to type.

- When you submit your query, two types of results are displayed: those close to your location, and those that are most similar to your search category.

- You then have the option to purchase tickets by clicking on a 'See Tickets' link.

- This takes me to an event page, where around 20 tickets are listed by price and can be filtered by attribute.

- Scrolling to the bottom of the list automatically loads another 20 or so.

- I then select the tickets I want and move on to purchase, which requires me to be signed in.

- I purchase my order through a 3rd party and receive a validation of payment.

## Metrics - NFL Opens Season
- Half a billion tickets sold per year = 1.3 million per day
  - upper limit of 2.5 million per day (taking average day and adding nfl schedule release amount)
  - lower limit of .5 million

- Assuming max of 2.5 million tickets sold in one day (750 writes per second)
- Assuming 200x reads per write
- Roughly 150k reads per second

- Double it during peak time (1500 writes per second, 300k reads per second)