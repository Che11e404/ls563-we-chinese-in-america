# ls563-we-chinese-in-america
Linked data project modeling individuals featured on the covers of We Chinese in America magazine, including multilingual name variants and links to external authorities.

**A. Dataset Description**

This dataset focuses on Chinese and Chinese Americans who appeared on the cover of We Chinese in America, a Chinese magazine published in San Diego that features news about the Chinese American community in Southern California (see https://wechineseus.com/index.php/english-section). The dataset is curated primarily from the descriptive metadata in the UC San Diego’s We Chinese in America Magazine Collection, which consists of digitized print issues published between 2001 and 2012 (see https://calisphere.org/collections/27980/). The dataset is supplemented with data from publicly available online sources.
The dataset contains 9 columns of property-value pairs and 56 entity rows. Individuals are modeled as the primary entities and are linked to the magazine issues in which they appeared. Each entity includes alternative name forms and external authority references, such as Wikidata identifiers and Library of Congress authorities. It is common for Chinese Americans to have a Chinese name, different romanized names, and a Western name used to navigate American society. The goal of this project is to connect name variants across languages to support improved searching and discovery of individuals featured on the magazine covers who have made significant contributions to their communities.

**B. Ontology and Controlled Vocabularies Used**

The data is structured using the RDF framework. Schema.org is used to model entities and relationships, including schema:Person and schema:CreativeWork at both the issue and title levels. The most commonly used name, or the form as it appears in the magazine, is recorded as schema:name, while other variants are recorded as schema:alternateName. Language tags (@en, @zh-Hans, @zh-Hant) are applied to represent names in different languages and scripts. Occupations are recorded using terms from Library of Congress Subject Headings (LCSH) to maintain consistency across the dataset.

**C. Linking Strategy**

Within the dataset, individuals are linked to the magazine issues in which they appeared using schema:subjectOf. Each person entity is also linked to external identifiers, including Wikidata entities and Library of Congress Control Numbers (LCCN) using schema:sameAs.

**D. Sample Triples**

Below are the sample triples for Maria Lixian Gee-Schweiger, who was featured on the cover of We Chinese in America Magazine four times. See “WeChinese_sample_RDF_graph.png” for the RDF graph of the sample triples.
```turtle
@prefix : <http://example.com/> .
@prefix schema: <http://schema.org/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix wechi: <https://example.org/wechinese/> .
@prefix vcard: <http://www.w3.org/2006/vcard/ns#> .
@prefix wd: <http://www.wikidata.org/entity/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .

wechi:bb0420000x  schema:url  <https://wechineseus.com/> ;
        schema:sameAs  wd:Q115044524 ;
        schema:name    "We Chinese in America Magazine"@en ;
        rdf:type       schema:CreativeWork .

wechi:p-geesch   rdf:type  schema:Person ;
        schema:name           "Gee-Schweiger, Maria Lixian"@en , "李岘"@zh-Hans , "李峴"@zh-Hant ;
        schema:alternateName  "Gee-Schweiger, Maria"@en , "Li, Xian"@en ;
        schema:sameAs         <https://lccn.loc.gov/no2003054130> , wd:Q113991352 ;
        schema:hasOccupation  "Authors"@en , "Television producers and directors"@en ;
        schema:subjectOf      wechi:bb5949066p , wechi:bb7826212c , wechi:bb72801334 , wechi:bb9908145z .

wechi:bb5949066p  schema:isPartOf  wechi:bb0420000x ;
        schema:url            <https://library.ucsd.edu/dc/object/bb5949066p> ;
        schema:datePublished  "2007-12"^^xsd:gYearMonth ;
        schema:volumeNumber   "7"^^xsd:int ;
        schema:issueNumber    "75"^^xsd:int ;
        schema:name           "We Chinese in America Magazine, Volume 7 Issue 75"@en ;
        rdf:type              schema:CreativeWork .

wechi:bb7826212c  schema:isPartOf  wechi:bb0420000x ;
        schema:url            <https://library.ucsd.edu/dc/object/bb7826212c> ;
        schema:datePublished  "2001-10"^^xsd:gYearMonth ;
        schema:volumeNumber   "1"^^xsd:int ;
        schema:issueNumber    "1"^^xsd:int ;
        schema:name           "We Chinese in America Magazine, Volume 1 Issue 1"@en ;
        rdf:type              schema:CreativeWork .
        
wechi:bb72801334  schema:isPartOf  wechi:bb0420000x ;
        schema:url            <https://library.ucsd.edu/dc/object/bb72801334> ;
        schema:datePublished  "2004-09"^^xsd:gYearMonth ;
        schema:volumeNumber   "3"^^xsd:int ;
        schema:issueNumber    "36"^^xsd:int ;
        schema:name           "We Chinese in America Magazine, Volume 3 Issue 36"@en ;
        rdf:type              schema:CreativeWork .
        
wechi:bb9908145z  schema:isPartOf  wechi:bb0420000x ;
        schema:url            <https://library.ucsd.edu/dc/object/bb9908145z> ;
        schema:datePublished  "2003-01"^^xsd:gYearMonth ;
        schema:volumeNumber   "2"^^xsd:int ;
        schema:issueNumber    "16"^^xsd:int ;
        schema:name           "We Chinese in America Magazine, Volume 2 Issue 16"@en ;
        rdf:type              schema:CreativeWork .
<https://lccn.loc.gov/no2003054130>
        schema:name  "Li, Xian, 1959-"@en .
```
