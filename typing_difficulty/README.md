# A Few Notes about Typing Difficulty

In the interest of time and getting a minimum feasible product created, I am using interkey intervals (the time between subsequent keypresses) as a proxy for "difficulty".  This is because bigrams with long inter-key intervals between presses could be considered more difficult than those with short intervals.  The compilation of this data is thanks to the collaboration of a number of researchers who were kind enough to share keystroke dynamics data with me from their own studies.  In this directory, you can find the [script I used to process their data](Compiling%20Keystroke%20Data.ipynb) as well as [the data set resulting from my culling and processing](bigram_info.csv). 

Anna Feit, a researcher at Finland's AAlto University, has recently conducted research on how people type (see http://userinterfaces.aalto.fi/how-we-type/) and has graciously shared some sample data with me.  As this data is not mine to share, I am only including in this directory the script that allowed me to go from her raw file to a processed csv consisting of the bigrams that are permutations of a-z, and their average interkey press time.

Anna Maria Feit, Daryl Weir, and Antti Oulasvirta. 2016. How We Type: Movement Strategies and Performance in Everyday Typing. In _Proceedings of the 2016 CHI Conference on Human Factors in Computing Systems_ (CHI '16). ACM, New York, NY, USA, 4262-4273. DOI=<http://dx.doi.org/10.1145/2858036.2858233>

Additionally, I am grateful to Vinnie Monaco for his collaboration in sharing two databases with me under a Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License.  The data is the product of the following research studies:

C. C. Tappert and S. Cha and M. Villani and R. S. Zack, "Keystroke Biometric Identification and Authentication on Long-Text Input", _Int. Journal Information Security and Privacy_ (IJISP) 2010.

Monaco, John V and Bakelman, Ned and Cha, Sung-Hyuk and Tappert, Charles C, "Developing a Keystroke Biometric System for Continual Authentication of Computer Users," _European Intelligence and Security Informatics Conference_ (EISIC) 2012.

Monaco, John V Monaco and Bakelman, Ned and Cha, Sung-Hyuk and Tappert, Charles C, "Recent Advances in the Development of a Long-Text-Input Keystroke Biometric Authentication System for Arbitrary Text Input," _European Intelligence and Security Informatics Conference_ (EISIC) 2013.
