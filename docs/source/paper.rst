Ur\_Namma, an OWL ontology of a sumerian grammar
================================================

:Authors:
  Sergio Alivernini [#]_
  Franco D'Agostino [#]_
  Marco Romano [#]_
  Luca Severini [#]_
:Version: latest
:Date: 11th July 2006

Foreword
--------

The construction of an ontology of the Sumerian language has been part
of a wider project of the company Epistematica for testing “Semantic Web
Technology” and its application on the computational linguistics. In
this context, the company has already completed a project, with the
collaboration of Dr. Marco Romano, to design an ontology of Esperanto to
demonstrate the possibility of realizing a linguistic parser with
reasoning skills. After this experience, it seemed appropriate to test
this procedure on a language that was not artificial like the Esperanto,
but natural; a language that had an evolving grammar and a more complex
history.

The Sumerian language flourished in a region called “Mesopotamia”
(between the two rivers Tigris and Euphrates in the modern Iraq)
documented from the half of IV millennium BC. It was spoken until the
end of III millennium when the Sumerian disappeared. But people that
during the centuries took the power in Mesopotamia continued to use it
as refined speech in the written documents until the II century AD given
its enormous literary, religious and political tradition.

The main characteristic of Sumerian is to be agglutinative, that is the
word (verb, substantive, adjective etc.) we read in a given text is
identical with the word we find in the vocabulary. In other words the
modifications (for example from singular to plural) do not change it
directly (like, for example in English dog → dogs); the specification of
the meaning happens with morphems added, agglutinated to the
unmodifiable word in a fixed order before or after it or by duplicating
a word (lugal = king → lugal-lugal = kings). This characteristic makes
it particularly suitable for the construction of an ontology due to an
easier identification of the morphemes.

The Research
------------

This project has been developed in two different steps: in the first one
a tutor (Dr. Marco Romano) taught me how to use the programs to manage
the ontologies OWL format: Protégé 3.2 e RacerPro 1.8, whilst in the
second one, the ontology was developed.

An ontology is composed by two elements: a T-Box (Terminological Box),
and an A-Box (Assertions Box). The T-box is the taxonomic part of
ontology, where concepts (and the hierarchy that exists among them) are
defined, and where we formalize the relationships hording between
different concepts. It is the “shape” of the ontology. The A-Box is the
part of the ontology that contains the facts, where individual instances
are classified as belonging to a specific class and where properties
that are defined for the classes are given a value for each instance. It
is the “substance” of the ontology. In the case of Sumerian, the T-Box
is the Sumerian grammar, while the A-Box is represented by every
Sumerian text that can be formalized in the grammar described in the
T-Box. Given the fact that this ontology represented an “experiment”, it
was decided not to use a long text, but one which could show some of the
most common grammatical features of the Sumerian language in order to
obtain a small but consistent and fully instantiated A-Box.

After analysing some texts the choice fell on a foundation brick of the
king Ur-Namma, king and founder of the Third Dynasty of Ur, who ruled in
Mesopotamia between 2112 and 2095 BC. The transliteration and
translation of the text is the follow:

.. tabularcolumns:: |1|p{5cm}|

+-------------------------------------------------+------------------------+
| :sup:`d`\ Nanna                                 | to the God Nanna       |
+-------------------------------------------------+------------------------+
| lugal-a-ni                                      | his king               |
+-------------------------------------------------+------------------------+
| Ur-\ :sup:`d`\ Namma                            | Ur-\ :sup:`d`\ Namma   |
+-------------------------------------------------+------------------------+
| lugal-Urim\ :sub:`5`\ :sup:`ki`-ma-ke\ :sub:`4` | king of Ur             |
+-------------------------------------------------+------------------------+
| e\ :sub:`2`-a-ni                                | his temple             |
+-------------------------------------------------+------------------------+
| mu-na-du\ :sub:`3`                              | he built               |
+-------------------------------------------------+------------------------+
| bad\ :sub:`3`-Urim\ :sub:`5ki`-ma               | the walls of Ur        |
+-------------------------------------------------+------------------------+
| mu-na-du\ :sub:`3`                              | he built               |
+-------------------------------------------------+------------------------+

This transliteration in Latin characters shows the value of each sign
that appears on the brick, but the reality of the grammar of this text
is not highlighted by this transliteration. To highlight the different
grammatical parts it is necessary that the scholars make a further
effort adding the elements that do not appear on the brick or joining
the signs that represent a unique grammatical element:

+----------------------------------------+
| Nanna.ra                               |
+----------------------------------------+
| lugal.ani                              |
+----------------------------------------+
| Ur-\ :sup:`d`\ Namma                   |
+----------------------------------------+
| lugal.Urim\ :sub:`5`\ :sup:`ki`.ak.e   |
+----------------------------------------+
| e\ :sub:`2`.ani.Ø                      |
+----------------------------------------+
| mu.na.n.du                             |
+----------------------------------------+
| bad.Urim\ :sub:`5`\ :sup:`ki`.ak.Ø     |
+----------------------------------------+
| mu.na.n.du                             |
+----------------------------------------+

This text represents our A-Box. The T-Box has been formalized based on
the grammar in this text. It is obvious that this text does not show all
the grammatical features of Sumerian language, that is the T-Box
developed here represents only a part of the grammar.

The Sumerian has two main structures: the nominal chain and the verbal
chain. Both are composed by different elements and their positions are
unmodifiable. So I have developed two classes “ElementsOfNominalChain”
and “ElementsOfVerbalChain”.

The “ElementsOfNominalChain” class
----------------------------------

In the Sumerian grammar the elements that compose the nominal chain are
six: noun, adjective, genitive, possessive, plural suffix ``-ene`` and
case. In our A-Box there were not all the six elements. As sub-classes I
took only the elements in the Ur-Namma brick foundation that is noun,
genitive, possessive and case. I added to this four sub-classes, a fifth
one “particle”, which was used to better define the “genitive”. Three of
these five sub-classes (possessive, case and particle) represent sets
that are numerically limited so I defined it with the elements that
composed it:

-  Possessive: ``gu10``, ``zu``, ``ani``, ``bi``, ``me``, ``zunene``, ``anene``

-  Case: ``e``, ``0``, ``ra``, ``da``, ``še3``, ``ta``, ``a``, ``gin7``

-  Particle: ``ak``

Moreover, to better define the sub-class “particle”, I created an
“object property” “FollowedBy” with the condition that the “particle” is
followed by the particle ``ak``; the sub-class “noun” was defined as a
word that is always followed by the “case”.

The “ElementsOfVerbalChain” class
---------------------------------

The verbal chain of Sumerian language is composed by eight elements:
modal prefixes, conjugation prefixes (here called simply “prefix”),
dimensional infixes, pronominal infixes, verbal root, suffix ``- ed``,
pronominal suffixes, postpositions. Even in this case, as already
written above, our A-Box does not contain all these elements. Our
sub-classes are therefore just the followings: Prefix, DimensionalInfix,
PronominalInfix and VerbalRoot; three of them are composed by a defined
number of elements:

-  Prefix: ``mu``

-  DimensionalInfix: ``na``

-  PronominalInfix: ``n``

The definition of “VerbalRoot” was, on the contrary, more complex. The
solution was to use the structure for position of Sumerian. So I defined
“VerbalRoot” as the elements of Verbal Chain that follow the
“PronominalInfix”. Therefore I created an “object property” “PrecededBy”
applying it to the “VerbalRoot” with the condition that it was preceded
by the sub-class “PronominalInfix”.

Conclusion
----------

As I said above, this ontology is only an experiment, an attempt, but
this work shows, however, that it is possible to apply the technologies
of the Semantic Web to a natural language as well. This seems to be the
right track and I am sure that these technologies will be able to
provide important new tools not only for Sumerian, but also for many
other linguistic aspects.

Annex
-----

.. note:: The ontology in OWL format **Ur\_Namma.owl**

------------------------

.. [#] PhD in Assyriology
.. [#] Assistant Professor of Assyriology at University of Rome Sapienza
.. [#] PhD in Logics and Informatics
.. [#] Founder of Epistematica, holder of the research project

|
|
