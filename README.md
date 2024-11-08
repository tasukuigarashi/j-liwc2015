# J-LIWC2015

## Overview

This repository explains how to analyze Japanese texts by J-LIWC2015. J-LIWC2015 is a Japanese-translated version of the LIWC2015 dictionary (Pennebaker, Booth, Jordan, & Blackburn, 2015). Psychometric properties of the J-LIWC2015 dictionary are introduced in [Igarashi, Okuda, & Sasahara (2022)](https://doi.org/10.3389/fpsyg.2022.841534).

Unlike English, there is no word boundary in a sentence in Japanese. It is mandatory for natural language processing to segment a Japanese text document into words before the main analysis. This repository provides basic instructions for using J-LIWC2015 and sample scripts for preprocessing texts for word segmentation.

## Steps to use J-LIWC2015 dictionary (for non-commercial use only)

Make sure you have downloaded one of the J-LIWC2015 dictionary files (valid serial number is required).

1. LIWC2015 format: `Japanese_Dictionary.dic`
   - available from http://www.liwc.net/dictionaries/
1. LIWC-22 format: `LIWC2015 Dictionary - Japanese.dicx`
   - available from https://www.liwc.app/dictionaries/

You can analyze Japanese texts in either of the following ways. Non-commercial users of the LIWC2015/LIWC-22 software can use the dictionary file in other programming languages (Python, R, etc.) with MeCab/IPADIC. This means that the users can seamlessly integrate the findings of preprocessing, main analysis, and postprocessing (optional) (see the example in Colab or R). Note that the developer does not formally support the use of the dictionary outside of the LIWC software (please do it at your own risk). The compatibility of the outputs generated by and outside of the LIWC software is also not guaranteed.

### LIWC-22 software

1. Main analysis: Use the LIWC-22 software with the J-LIWC2015 dictionary (`LIWC2015 Dictionary - Japanese.dicx`) for category-by-category word frequency analysis. Wword segmentation is conducted internally.

### Python + LIWC2015 software

-  Python (Colab) (LIWC2015 dictionary format): [Preprocessing and postprocessing](https://colab.research.google.com/drive/1iMm0ZvVZttJ9PzYdSUiBjtIXL7_gZEC3) (by [@soramame0518](https://github.com/soramame0518) and [@okudashi](https://github.com/okudashi))

1. Preprocessing: Analyze a Japanese text (e.g., `sample.txt`) by [MeCab/IPADIC](https://taku910.github.io/mecab/) with `user_dict.dic` (in this repository) in Python. In the example in Colab, two output files are generated:
   - `wakachi.txt`: word segmentation output
   - `pos_rate.txt`: POS tagging output
1. Main analysis: Run the LIWC2015 software, click `Dictionary` → `Load New Dictionary`, and choose `Japanese_Dictionary.dic`. Then analyze `wakachi.txt` (word segmentation output). An output file is:
   - `LIWC2015 Results (wakachi).txt`: word frequency analysis output
1. Postprocessing (optional): Combine `LIWC2015 Results (wakachi).txt` (word frequency analysis output) with `pos_rate.txt` (POS tagging output) so that users can obtain more detailed information about POS of the text (see the example in Colab). A merged output file is:
   - `result.txt`: word frequency and POS tagging output

### Python only

- Python (Colab) (LIWC2015 dictionary format): [Preprocessing, main analysis, and postprocessing](https://colab.research.google.com/drive/1bX-JyY4xmCm_RFkJg3QNcthUvEJaBghP) (by [@soramame0518](https://github.com/soramame0518) and [@okudashi](https://github.com/okudashi))

### R only

- R (LIWC2015 and LIWC-22 dictionary formats): The [jliwc](https://github.com/tasukuigarashi/jliwc) package can be used for preprocessing, main analysis, and postprocessing. MeCab/IPADIC and the user dictionary will be automatically installed and a POS tagging output will be included in the results of the main analysis. See [Analyzing Japanese texts with R and J-LIWC2015](https://tasukuigarashi.github.io/j-liwc2015-R/) for a tutorial in Japanese.

## Notes

Any request for the distribution of the dictionary file is not accepted. Questions about the commercial use of J-LIWC2015 should be directed to [Receptiviti](https://www.receptiviti.com/contact).

## Reference

Igarashi, T., Okuda, S., & Sasahara, K. (2022). Development of the Japanese Version of the Linguistic Inquiry and Word Count Dictionary 2015. Frontiers in Psychology, 13:841534. [https://doi.org/10.3389/fpsyg.2022.841534](https://doi.org/10.3389/fpsyg.2022.841534)

## Licence

MIT
