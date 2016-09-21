# SAMPLE demos from AMI as dataTables

These are a few demos of what the AMI tools can create for searching EuPMC. 
## how these were created

Most  projects were created with one-word searches using `getpapers` on EuPMC to create a `CProject` with the name as the term. Then the
`cProject` was normalized and the facets extracted in a single step. 

```
getpapers -q aardvark -o aardvark -x -p 
```  
queries EuPMC for `aardvark` and creates a `cProject` `aardvark`. Then cmine is run with a default set of bioscience dictionaries.
```
cmine aardvark
```
which creates the snippets files and a summary in `full.dataTables.html`.

### links to wikipedia

The snippets (facts) are linked to hypothetical Wikipedia articles (e.g. from `aardvark` we create the link`<a href="http://en.wikipedia.org/wiki/Aardvark">Aardvark</a>`). In some cases the item is not in Wikipedia and gives a "not found" page, but a surprisingly high percentage are. The use of `wikidata` will be a major enhancement.

### links through wikidata

We are now converting our bioscience dictionaries to have Wikidata ids. This will mean that e can create links only when there is a Wikidata ID  and there is guaranteed to be a link to the Wikipedia page. We have about 15 current dictionaries and will re-run the analysis shortly

## tables

The tables are created with columns corresponding to:

 * the PMC identifier and a link to the paper
 * a variety of "facets" either from dictionaries or from regexes
 * a summary of the most frequent words (with stop words ("the, of, etc.") omitted)

### table display
The display uses the DataTables JS package enhancement which adds table management (e.g. chunking the display, search etc.). This is automatically downloaded from the web. It won't display directly from the github site. Without the DataTables the display is a well-formed HTML table, just not interactive

## Examples

### aardvark

```
getpapers -q aardvark -o aardvark -x -p
```

The headings are:






