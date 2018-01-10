# Key Terms and Concepts

## Extractors

Within our platform, an "extractor" is a model for extracting data from a given website on the internet.  An extractor definition is composed of the source(s) of data and the output schema to which the site data is mapped. 

### Data Source(s)
An extractor's source of data may a single page/URL or be composed of many different pages/URLs within the site context.  

It may also be defined as a series of interaction steps, which may include authentication, form submissions, javascript-driven user interactions (ie. scrolling and/or clicking), and all of the pages/URLs visited via these means.  

### Training
The source(s) for extractor data are defined through the Import.io application which allows you to "train" extractors via our interface.  Training is what connects elements on the page to the resulting output schema that you define.  If a page contains a microdata schema definition (http://schema.org/docs/gs.html), we will use that to suggest an output schema mapped to that definition.  If not, we will attempt to suggest schema/mapping based on the underlying DOM (Document Object Model) schema of the page.  

You can always clear our suggested training and replace with your own schema/mapping, or modify the suggested training until you are mapping all page data required for your needs.  There's incredible diversity in how websites present data, so we have many advanced features (xpath definitions, etc.) as well as a CS (Customer Success) team to help users successfully train against nearly any site. 

As noted above, extractors can also be trained to use page interaction, where you use the application to record a series of user interactions with the page that we'll then replay and save. Users define at what points in the sequence they would like to extract data in a similar fashion to defining multiple pages/URLs within a site context.

The output schema contains column/field definitions that may include text or images.  If the text/image content contains links, you'll be asked whether or not to include the associated link as an additional column/field. 

## Crawl Runs
A "crawl run" is the resulting set of data from an extractor being invoked by the platform.  

Crawl runs may be scheduled at any interval.  Every page/URL or data extract point is treated as a "query" within the platform.  Each level of user account has a maximum number of queries that may be processed within a calendar month.  

You may opt to have each query take a screenshot of the page content from which it was extracted, in PDF or PNG format, but this will cost an additional query for each screenshot thus generated. 

## Reports

## Our Platform

## Our Approach 