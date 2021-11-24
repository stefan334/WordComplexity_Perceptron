# WordComplexity_Perceptron
Perceptron

Modelul Perceptron primeste elementele din datele de antrenare, avand ca scop sa invete setul de ponderi w0, w1 ,..., wn astfel incat clasa elementelor sa fie prezise corect. Folosind aceste ponderi, perceptronul poate calcula o suma ponderata a feature-urilor pentru a determina valoarea clasei elementului ce trebuie prezis. Pentru acest model au fost folosite toate valorile default ale modelului Perceptron care apartine librariei sklearn.

 (https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Perceptron.html)

 

Features:

Features-urile folosite au fost grupate in mai multe categorii: word_structure_features, corpus_feature, context_features, wordnet_features.

Word_structure_features:

·       isDaleChall – clasifica daca un cuvant face sau nu parte din lista de cuvinte DaleChall, alocand valoarea 1 daca acesta face parte, si valoarea 0 daca nu. DaleChall este o lista de cuvinte ce sunt considerate a fi “simple”.

·       isTitle – clasifica daca un cuvant este sau nu titlu, mai exact verifica prima litera a cuvantului, putand lua valoarea 1, daca prima litera este majuscula, si 0 daca nu.

·       nrSyllables – calculeaza numarul de silabe al cuvantului, folosindu-ne de libraria pyphen.

·       Len – calculeaza lungimea cuvantului

·       nrVowels – calculeaza numarul de vocale din cuvant, astfel in cat un numar de vocale ridicat poate creste dificultatea fonetica a cuvantului.

Corpus_feature:

·       Corpus – Ia in considerare corpusul din care face parte cuvantul, putand a se observa o diferenta in dificultatea cuvintelor in functie de corpusul lor, astfel cuvintele din corpusul “bible” pot fi considerate mai simple, iar cele din “biomed” pot fi considerate, on average, mai complexe.

Context_feature:

·       nearbyWords – Verifica contextul in care se afla cuvantul, astfel ia intreaga propozitie si verifica daca cuvintele din ea apartin sau nu listei DaleChall, facand o medie intre toate valorile cuvintelor din propozitie si rotujind, putem determina daca contextual in care se afla este unul complicat (1) sau simplu (0).

Wordnet_features:

·       nrSynsets – Verifica cate categorii de cuvinte care sunt sinonime cu cuvantul respective exista.

·       getHyponyms – Verifica cate hyponyme exista pentru cuvantul dat.

·       getHypernyms – Verifica cate hypernyme exista pentru cuvantul dat

·       getMeronyms_parts(_substances) – Verifica din cate parti este compus obiectul reprezentat de cuvant, dar si din cate materiale este format.

·       getHolonyms_parts(_substances) – Verifica din cate grupuri face parte obiectul reprezentat de cuvant.

 

In total vom avea 14 feature-uri, care inainte de a fi aplicate peste model vor fi normalizate folosind functia preprocessing.normalize().

Folosindu-ne de aceste atribute si acest model, am reusit sa atingem o acuratete de 0.78185.
