# Trump Campaign Speech and Debate Transcripts

This is a semi-structured version of the transcripts of Donald Trump's campaign speeches and debate transcripts, as provided by the [The American Presidency Project](http://www.presidency.ucsb.edu/index.php) at UC Santa Barbara. This dataset includes 74 documents comprised of approximiately 292,000 words of oral speech.

The speeches (called "Remarks" on the USCB site, [source page](http://www.presidency.ucsb.edu/2016_election_speeches.php?candidate=45&campaign=2016TRUMP&doctype=5000)) are transcribed verbatim from the site. Although I have not verified how exhaustive the list of speeches is, this dataset contains a large number of Trump's campaign rally speeches from June 2015 through November 2016. It also includes his Republican Convention acceptance speech in July 2016. 


The debate transcripts ([source page](http://www.presidency.ucsb.edu/debates.php)) have been processed to include only the portions of the transcript attributable to Donald Trump.

The transcripts are in markdown files with YAML frontmatter. 

```yaml
---
date: '2016-08-09'
description: Remarks at a Rally at the University of North Carolina in Wilmington
location: Wilmington, North Carolina
source: http://www.presidency.ucsb.edu/ws/index.php?pid=122534
type: speech
---

The crowds we're getting -- I'm the messenger, but I'll tell you what, the message is the right message. We're tired of incompetence. We're tired of not taking care of our military. We're tired of not taking care of our vets, who are being taken care of very poorly. We're tired of so many different things. And this is what happens. So, our mayor, my friend, Rudy Giuliani just walks, I'm t [ ... etc. ... ]
```

If you're using Python, reading the data with the `python-frontmatter` package is highly recommended. (See [source repo](https://github.com/eyeseast/python-frontmatter) for more instructions.)




```python
import frontmatter
speech = frontmatter.load("./transcripts/speech_2016-08-09.md")

print(speech.metadata)
```
```python
{
  'date': '2016-08-09',
  'source': 'http://www.presidency.ucsb.edu/ws/index.php?pid=122534',
  'type': 'speech', 
  'description': 'Remarks at a Rally at the University of North Carolina in Wilmington',
  'location': 'Wilmington, North Carolina'
}
```

```python
print(speech.content[0:200])
```
```python
The crowds we're getting -- I'm the messenger, but I'll tell you what, the message is the right message. We're tired of incompetence. We're tired of not taking care of our military. We're tired of not
```
