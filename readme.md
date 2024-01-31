### This repository contains files associated to two papers:

```
@inproceedings{zilio2018sla,
  title={An SLA Corpus Annotated with Pedagogically Relevant Grammatical Structures},
  author={Zilio, Leonardo and Wilkens, Rodrigo and Fairon, C{\'e}drick},
  booktitle={Proceedings of the Eleventh International Conference on Language Resources and Evaluation (LREC-2018)},
  pages={4120-4126},
  year={2018},
  url={https://aclanthology.org/L18-1650.pdf}
}

@inproceedings{zilio2018analyzing,
  title={Analyzing grammatical structures in texts written by language learners},
  author={Zilio, Leonardo and Wilkens, Rodrigo and Fairon, C{\'e}drick},
  booktitle={Proceedings of CALL your DATA (CALL 2018)},
  pages={381-388},
  year={2018},
  url={https://www.researchgate.net/profile/Alberto-Andujar/publication/329280587_Telecollaboration_through_WebRTC_Building_bridges/links/5c0030f6299bf1a3c1560c08/Telecollaboration-through-WebRTC-Building-bridges.pdf#page=381}
}
```


Readme for the files associated with the SMILLE annotation of EFCAMDAT:

There are three files in total:

- cambridge.smille.filtered.csv.tar.bz2
- cambridge.smille.filtered.rand.csv.tar.bz2
- cambridge1.xml
- cambridge2.xml

The first two files contain a CSV with the vectors for each document from EFCAMDAT. Both files are filtered: they only contain documents from EFCAMDAT that had a score above 80 (their grade according to the Cambridge evaluators was above 80). The second file is a more balanced, random selection of texts that was balanced along the CEFR levels (from A2 to C1). The filter of scores above 80 was used to avoid parsing errors interfering with the annotation, since texts that got lower scores tend to be harder to parse and to annotate.

In these two files, there are only vectors. The first column of the csv is an ID that corresponds to the ID of the text in the EFCAMDAT, and the other number correspond to the value of the given tag.

The last two of these files are XML samples that contain a document annotated with SMILLE tags. These file also have the text ID and other basic information from EFCAMDAT, but they have the annotation of tags for each word in the document, as opposed to the document vectors in the CSV files.

In the XML files, the structure goes from a "text" tag that ancompasses each document and contains information about it from EFCAMDAT. An example of this kind of information would be:

```
<id>C17862</id><level>10</level><unit>3<unit><learner_nationality>cn</learner_nationality><topic_id>274</topic_id><grade>84</grade><level>10</level>
```

There one can see the ID, Cambridge level, unit, nationality, topic and grade of the learner/document.

Each "text" tag then contains several "p" tags, for each paragraph in the document, and each "p" tag contains several "smilleTag" for each sentence. In the "smilleTag", you can find sentence length information as an attribute and, inseide the tag, there are several "smilleSpan" tags for each word. Inside the "smilleSpan" tag, the class attribute contains the SMILLE annotation for it. Each tag is formed by the tag name (e.g. sm_LEX_NNS) and an identifier (e.g. 0.22) which is unique inside the document; both are separated by an underline ("_"), so that the full tag would be, for instance "sm_LEX_NNS_0.22".