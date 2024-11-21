# Notes

This repo will become more structured along the way

## BDX IO

### Rex scale-up: les impacts du passage à l'échelle ⭐
https://app.imagina.com/bdx-io/content/26551174

Migration Play->Spring Boot : faire un Business case, bien analyser le cout et les impacts, roadmapper
Migration -> ajout de nouvelles applis en monorepo hors du monolithe


Transverse Technique oublié : Comment gérer ? -> Equipe dédié.

Prioriser via [Cost Of Delay](https://www.productplan.com/glossary/cost-of-delay/) : quantifier le cout de reporter la feature 🔥


### Causalité et statistiques, un amour pas si impossible que ça ⭐⭐⭐
https://app.imagina.com/bdx-io/content/26551479
[Denis Maurel](https://github.com/Kahss) (One Point)

Causalité : lien avec la probabilité P(X | Y)
P(cholesterol | velo) : haute, car il y a une "variable confondante". Ici l'Age par exemple. 

> En statistique, un facteur de confusion, ou facteur confondant, ou encore variable confondante, est une variable aléatoire qui influence à la fois la variable dépendante et les variables explicatives.

[Do-calculus ou Causal Calculus](https://en.wikipedia.org/wiki/Causality#Causal_calculus) : probabilite d'une variable sachant une autre, en indépendance.
"Causal Model" : Graphe de variable (acyclique)

*Judea Pearl*: [The Book of Why](https://en.wikipedia.org/wiki/The_Book_of_Why)

*Ilya Shpitser* : décomposition d'un do-calculus en un ensemble de predicteur étant donné un graphe de causalité.  
Prédicteur : P(X | Y,Z, ...) -> Estimation d'une desnité de probabilité -> Modèle d'IA  
Modèle d'IA : peut-être aussi simple qu'une régression (est c'est bien car **explicable**)

"Tous les modèles sont faux, certains sont utiles"- Georges Box 🔥

### Le coût du Mob Programming ⭐⭐
https://app.imagina.com/bdx-io/content/26551874
[Hadrien Mens-Pellen](https://github.com/hadrienmp)

Mesurer, mesurer, mesurer.  
La véolicité, le nombre de bugs, le kiff.

Dev standard : ~  8 SP de Velocité, pas prédictible car beaucoup de bug, kiff moyen
Mob : ~  6 SP de Velocité, pas de bug, kiff de ouf. Overhead au démarrage.
Onboarding : hyper facile avec le Mob.

+ Personne n'est indispensable
+ Connaissances partagée
+ Design collégial
+ Pas besoin de PR
+ Kiff
+ Prédictible : Cool pour les PO 🔥
- Un peu d'overhead

Suppression du Mob par le CTO :
- Pas possible de revenir à la vélocité orginale.

[Mob Programming Toolbox](https://youtu.be/wK4PL3RsskA?si=2uO10jaAIg4OtWGt)


### Karpenter, le futur de la gestion des noeuds Kubernetes
https://app.imagina.com/bdx-io/content/26552389

Karpenter : gestion des noeuds Kubernetes
2 CRD : NodeClass, NodePool

Remplace la gestion des nodes via des AutoScaling Groups.

Meilleure allocation
Possibilité de définir un TTL pour les noeuds : Chaos Engineering.

https://karpenter.sh/

### Comment utiliser le NoCode comme un microservice dans une architecture logicielle complexe ⭐
https://app.imagina.com/bdx-io/content/26553707

Architecture logicielle pas si complexe que ça.
Key Takeaways : mettre un Service devant comme sidecar, utiliser PubSub.

### Accélérer sa transformation DevOps en 2025 avec Accelerate ⭐⭐⭐
[Jean-Rémy Révy](https://github.com/jrrevy) (Head Of Architecture @Ippon) 
https://app.imagina.com/bdx-io/content/26553896

[Slides](https://fr.slideshare.net/slideshow/bdx-io-2024-accelerer-avec-accelerate-en-2025/273100665)

DORA Quick Check : https://dora.dev/quickcheck/ -> "Create a Sense of Urgency" (John Kotter) 🔥
Organiser un [Value Stream Mapping](https://en.wikipedia.org/wiki/Value-stream_mapping)
Lire le [State of DevOps Report 2024](https://cloud.google.com/resources/devops/state-of-devops?hl=en) 
[DX Core 4](https://getdx.com/research/measuring-developer-productivity-with-the-dx-core-4/) : DORA + Space + DevX 🔥
[Loi des rendements décroissants](https://fr.m.wikipedia.org/wiki/Loi_des_rendements_d%C3%A9croissants)

[Dora Capabilities](https://dora.dev/capabilities/) regroupées en 3 catégories : Climate for Learning, Fast Flow, Fast Feedback 🔥

### Sécurité automatisée: Regardez vos failles en face ⭐⭐
[Marine du Mesnil](https://github.com/marine-mb)

QRQC (Quick Response Quality Control) aka Dantotsu 🔥

> Le QRQC signifie Quick Response Quality Control, ce qui se traduit par Contrôle Qualité à Réponse Rapide. C’est une méthode de résolution de problèmes qui combine le contrôle qualité, l’amélioration continue, et le travail d’équipe pour résoudre les problèmes de qualité dans un environnement industriel. C’est une approche structurée qui consiste à identifier le problème, analyser sa cause racine, traiter les anomalies, mettre en œuvre des actions correctives, et vérifier leur efficacité.

[QRQC](https://shizen.io/le-qrqc-qu-est-ce-que-c-est-4-etapes/#:~:text=Le%20QRQC%20signifie%20Quick%20Response,qualit%C3%A9%20dans%20un%20environnement%20industriel.)

[Sécurité automatisée: Regardez vos failles en face(YT) ](https://www.youtube.com/watch?v=k7DxL5w8fm8)

### Alerte, tout brûle ! Comment gérer des incidents techniques ⭐⭐⭐

Définition d'incident 🔥
> Si quelqu'un pense que c'est un incident, c'est que c'en est surement un

Définir un Incident Commander

Ne pas passer plus de temps à évaluer la sévérité qu'à traiter l'incident 🔥
> sev4->sev1 au jugé, arrondi sup

[Slides](https://fr.slideshare.net/slideshow/alerte-tout-brule-comment-gerer-des-incidents-techniques-breizhcamp-2024-2024-06-28/269945182)

### Formation Arolla - Domain Driven Design

Importance de la communication
https://www.infoq.com/minibooks/conversation-patterns/

"C'est la compréhension du métier par les devs qui part en prod"
Manière de vendre le DDD

Dev et PM au même niveau


-> Connaissance Métier 
-> Extraction
-> Modélisation (abstraction = compression avec perte -> dans le but de garder compréhensible maintenable)
-> Code


DDD Code
 - No Frameworks, No Logger, No SQL
 - No Nulls : Optional<Object>, Null Object Pattern

Object Calisthenics

Le code sert de vélo pour le cerveau -> Le code donne des insights sur le métier (ex. bug -> traduit un manque métier)

Differentiateur : DDD
Pas differentiateur : pas DDD, mais surtout à ne pas coder soi même 
Dans ce cas là on s'adapte au process de l'outil choisi.


Heuristiques de découpage : 
 - Champs Lexicaux
 - Purpose
 - Gestion des dépendances (Runtime : instrumentation, Static : commit correlation)
 - Caractéritistiques techniques (Taille, Disponibilité, Pression)
 - Nature (Logical, Physical, Potential, Symbolic ...)
 - Cardinalité : Singular, Plural
 - Descriptif vs Prescriptif

PIM : Product Inventory Management


## Notes

Taking notes : 
- Safari des mots : souligner les nouveaux mots
- Guetter les synonymes et demander à préciser la différence
- Avoir un minimum de connaissance
- Challenger

"Le danger d'une communication c'est l'illusion qu'elle s'est bien passée"

souligner les mots nouveaux / remarques entre [] / questions avec "?" ou "Q:"
Prioriser les questions
-> Why ?
Faire préciser le but, et remonter au vrai but

Question Everything. Why ?

Toujours demander un Exemple concret

"Dans quel cas ce serait pas vrai ?" : les invariants donnent de bonnes indications de concepts supplémentaires

Creuser un domaine : Synonyme et Invariant

Synonyme -> Différents Bounded Contexts

"Cunningham's Law"
Cunningham is credited with the idea: "The best way to get the right answer on the Internet is not to ask a question; it's to post the wrong answer."



Le dernier mot au PM en cas de désaccord

Obsession DDD : 
 - le langage
 - la réalité (comme elle est et pas comme on voudrait)
 - l'identification (pas de traduction, mapping métier-technique 1 pour 1)

Ennemi n1 : le coût de coordination



Seperate ways
Integration : Upstream / Downstream -> dépendant du flux de valeur (indépendant du sens des données au de qui appele qui )
Api d'envoi de sms, on envoie des données pourtant on est downstream.

# Design Tactique

Classe qui raconte le métier 
Signal to Noise Ratio >= 80%

CashFlow vs CashFlow*Builder*

Object Newable vs Injectable
VO / Entity : Newable
Service : Injectable


#### Notes de Laurent
(à synthétiser avec le reste)
DDD - Domain-Driven Design

* Consolider les connaissances sur DDD
* Pratiquer
* Aggrégats
* Maîtriser la relation entre DDD et architecture Hexagonale
* Considérations transverses: sécu, login, autorisation
* Comment découper efficacement un bon view monolithe ?
* Outils de mise en pratique ? Collaboration avec Q.A./P.M. ?
* Pattern techniques => code de qualité
* Contexte Praxedo
* Bonne pratiques ownership des équipes

Event Storming
- Aller chercher la connaissance du métier chez tout le monde.
- Rendre visible le savoir grâce à la variété de personne.
- Experts officiels: PM
- Experts officieux: utilisateurs, clients, support, développeurs, vécu
- Accès à l'expertise: questions, observations, mesures, littérature, concurrence, le code existant
- Pas de confiance à 100% à l'expertise: verbeux, pas tout à fait adapté, mal nommé
- Les domaines métiers ont tous des points communs (cf. Martin Fowler)
- Passer d'un domaine à l'autre n'est qu'un effort minime (20%

Abstraction
- Généralisation des exemples (Persona, Concept)
- Modéliser (compression d'histoires) en ne gardant que le concentré du savoir métier
- Compression du savoir pour faire émerger des concepts

Approche DDD
- Tout le monde doit participer
- L’expertise est partagée et diffusée

Phases:
- Extracting
- Crunching/Modeling
- Code
- « Rinse and Repeat »

Un bon modèle est celui qui répond le mieux aux besoins et reste simple.
Un modèle qui généralise est un modèle qui gomme.
Toujours considérer plusieurs modèles pour éviter l’effet d’enfermement.

Ubiquitous Language
- Le language est restreint au domaine
- Nommer les choses, c’est déjà les modéliser

Objets calisthéniques
- Règles à la con qui marchent à tous les coups.

BDD: Behavior-Driven Design (art des conversations)
TDD: Test-Driven Design (écrire les tests avant le code)

Le code est comme un vélo: il démultiplie la force d’esprit.

Définition d’un pantalon:
- vêtement allant de la taille aux chevilles, couvrant les jambes séparément.

L’expérience est souvent tacite (difficilement accessible ou explicable).
- une solution est de proposer des extrapolations et de voir si il y a des contre-exemples: soit on les ignore, soit on les intègre au modèle.

Si le domaine est différentiateur, alors DDD.
Si le domaine n’est pas différentiateur, alors pas DDD. Standardisation.

Strategic Design

Bounded Contexts:
- Contexte linguistique dans le lequel les mots ont un sens précis.

Ex. Marketing:
- facile à convaincre
- fidèle
- facilement identifiable (ciblage)
- réceptifs à la publicité (tendance à cliquer sur les pubs)
- influenceur chaussures de sécurité

Bounded Contexts => Champs Lexicaux
Identifier le but de chaque contexte => Verbes

Découpage suivant les champs lexicaux

Autre découpage possible: instrument & blame pour identifier les clusters de code.
Découpage efficace si 80% de modifications sont localisées.
Découpage permet d’utiliser des languages/technologies différentes
Découpage permet le scaling indépendant
Si dans un domaine, il existe des asymétries, c’est une opportunité de découpage.

Interview des experts
- Word Safari: souligner les mots nouveaux. Demander la définition.
- Les mots nouveaux sont synonimes ? Demander la différence.
- Avoir un minimum de connaissance pour mériter le temps de l’expert.
- Montrer de la curiosité
- Poser de meilleures questions
- Challenger les réponses
- Paraphraser pour vérifier la compréhension

Ex:
Membre association Agile France
Association Loi 1901 3 bénévoles
But promotion agilité
Membres cotisation
Liste dans un Excel dans un dropbox (3 bénévoles + 2 volontaires)
Cotisations financent des actions de l’association
Pas d’actions claire
But solidarité en cas de coup dur pour les membres qui font la promotion
200 membres
Aide la conférence Agile France
Association avance trésorerie pour l’organisation de la conférence Agile France
Durée cotisation 1 an
Billetterie conférence Agile France ouverte à tous
Remise aux membres de l’association (~= cotisation association)
Membre (n’a pas forcément payé) / Adhérent (a payé)

Domain Expert
Toujours demander le dernier mot aux experts (rassure)

Downstream Upstream
- Code dependencies
- Org/Team dependencies
- Power relationship

Conformist => Easy but no autonomy
Anti-corruption Layer => Expensive but autonomy

Legacy => use ACL
Translation => use ACL
Don’t know => Conformist
Going fast => Conformist
Diversity => use ACL
Rich domains => use ACL

Tactical Patterns

Agrégats et Invariants
Partir large puis réduire en fonction du contexte.

## Resources

- [The 8 Steps for Leading Change - John P. Kotter](https://www.kotterinc.com/methodology/8-steps/)
- [Leading change - John P. Kotter](https://www.amazon.fr/dp/1422186431)
- [Analysis Patterns: Reusable Object Models
](https://www.oreilly.com/library/view/analysis-patterns-reusable/9780134271453/)
- [Software Design X-Rays - Adam Tornhill](https://pragprog.com/titles/atevol/software-design-x-rays/)
- [CodeScene](https://codescene.com)
