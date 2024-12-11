# Formation Arolla - Domain Driven Design

## Objectifs

* Consolider les connaissances sur DDD
* Pratiquer
* Aggrégats
* Maîtriser la relation entre DDD et architecture Hexagonale
* Considérations transverses : sécu, login, autorisation
* Comment découper efficacement un bon view monolithe ?
* Outils de mise en pratique ? Collaboration avec Q.A./P.M. ?
* Pattern technique -> code de qualité
* Contexte Praxedo
* Bonnes pratiques d'ownership des équipes

## La Connaissance du Domaine

> It's developers (mis)understanding that's released in production, not the experts' knowledge
> Alberto Brandolini

Approche DDD
- Tout le monde doit participer
- L’expertise est partagée et diffusée
- Dev et PM au même niveau dans cette pratique.

Obsession DDD :
- le langage
- la réalité (comme elle est et pas comme on voudrait)
- l'identification (pas de traduction, mapping métier-technique 1 pour 1)

Phases:
- Extracting
- Crunching/Modeling
- Code
- « Rinse and Repeat »

### Extraction

Event Storming
- Aller chercher la connaissance du métier chez tout le monde.
- Rendre visible le savoir grâce à la variété de personne.
- Experts officiels: PM
- Experts officieux : utilisateurs, clients, support, développeurs, vécu
- Accès à l'expertise : questions, observations, mesures, littérature, concurrence, le code existant
- Pas de confiance à 100% à l'expertise : verbeux, pas tout à fait adapté, mal nommé
- Les domaines métiers ont tous des points communs (cf. [Analysis Patterns: Reusable Object Models
  ](https://www.oreilly.com/library/view/analysis-patterns-reusable/9780134271453/))
- Passer d'un domaine à l'autre n'est qu'un effort minime (20%)

#### Gestion de la Conversation

[Conversation Patterns](https://www.infoq.com/minibooks/conversation-patterns/)

- Word Safari: souligner les mots nouveaux. Demander la définition.
- Guetter les synonymes et demander à préciser la différence
- Avoir un minimum de connaissance pour mériter le temps de l’expert.
- Challenger les réponses
- Montrer de la curiosité
- Poser de meilleures questions / Prioriser
- Paraphraser pour vérifier la compréhension
- Toujours demander un Exemple concret
- **Pourquoi ?** Faire préciser le but, et remonter au vrai but
- "Dans quel cas ce ne serait pas vrai ?" : les invariants donnent de bonnes indications de concepts supplémentaires
- Toujours donner le dernier mot aux experts (rassurant)
- Creuser un domaine : **Synonymes** et **Invariants**
- Synonymes -> Différents Bounded Contexts

Prise de note :
- Souligner les mots nouveaux
- Remarques entre []
- Questions avec "?" ou "Q:"


> The greatest problem of communication is the illusion that it has been achieved.  
> *William H. Whyte*

> Cunningham's Law : The best way to get the right answer on the internet is not to ask a question; it's to post the wrong answer.  
> *Ward Cunningham*


L’expérience est souvent tacite (difficilement accessible ou explicable). 
Une solution est de proposer des extrapolations et de voir s'il y a des contre-exemples.  
Soit on les ignore, soit on les intègre au modèle.

### Modélisation

Abstraction
- Généralisation des exemples (Persona, Concept)
- Modéliser (compression d'histoires) en ne gardant que le concentré du savoir métier
- **Compression** du savoir pour faire émerger des concepts
- Compression pour garder maintenable

Un bon modèle est celui qui répond le mieux aux besoins et reste simple.
Un modèle qui généralise est un modèle qui gomme.
Toujours considérer plusieurs modèles pour éviter l’effet d’enfermement.

> All models are wrong, but some are useful.
> *George E. P. Box*


### Code

DDD Code
- No specific language
- No Frameworks, No Loggers, No SQL
- No Nulls : Optional<Object>, Null Object Pattern
- No Exceptions

Le code est comme un vélo : il démultiplie la force d’esprit.
Le code donne des insights sur le métier (ex. bug -> traduit un manque métier)


## Strategic Design

### Ubiquitous Language

- Le langage est restreint au domaine
- Nommer les choses, c'est déjà les modéliser

### Bounded Context

Contexte linguistique dans le lequel les mots ont un sens précis.  
Bounded Contexts => Champs Lexicaux  
Identifier le but de chaque contexte => Verbes

Ennemi n°1 : le coût de coordination

![A picture representing fully connected graphs at various vertices number, illustrating coordination cost](/assets/team_coordination_fully_connected_graph.webp)

Isoler le langage et les concepts dans des Contextes séparés.
Limite le cout de Coordination

Bounded Context ~= Sous-domaine 
- Sous-domain : Espace du problème
- Bounded Context : Espace de la solution

Différenciant : DDD  
Pas Différenciant : pas DDD, mais surtout à ne pas coder soi-même.  
Dans ce cas-là, on s'adapte au process de l'outil choisi.

Heuristiques de découpage :
- Champs Lexicaux
- But
- Gestion des dépendances (Runtime : instrumentation, Static : commit correlation)
- Caractéristiques techniques (Taille, Disponibilité, Pression)
- Nature (Logical, Physical, Potential, Symbolic ...)
- Cardinalité : Singular, Plural
- Descriptif vs Prescriptif
- [Independent Service Heuristics](https://github.com/TeamTopologies/Independent-Service-Heuristics)

- Découpage efficace si 80% de modifications sont localisées.
- Découpage permet d’utiliser des languages/technologies différentes
- Découpage permet le scaling indépendant
- Découpage = Opportunité pour l'Entreprise

Si dans un domaine, il existe des asymétries, c’est une opportunité de découpage.

PIM : Product Inventory Management

### Collaboration (Context Mapping)

**Separate ways**

**Upstream Downstream**

Upstream / Downstream -> dépendant du flux de valeur (indépendant du sens des données ou de qui appelle qui).  
*Ex. Analogie du caca dans la rivière : celui qui est upstream n'est pas impacté*  
*Ex. Api d'envoi de SMS, on envoie des données pourtant on est downstream.*  

- Code dependencies
- Org/Team dependencies
- Power relationship

- Conformist => Easy but no autonomy
- Anti-corruption Layer => Expensive but autonomy

Legacy => use ACL  
Translation => use ACL  
Don’t know => Conformist  
Going fast => Conformist  
Diversity => use ACL  
Rich domains => use ACL

## Tactical Design

Classe qui raconte le métier

Signal to Noise Ratio >= 80%

CashFlow vs CashFlow*Builder*

Object Newable vs Injectable
- Value Objects / Entity : Newable
- Service : Injectable

Objects Calisthenics
- Only One Level Of Indentation Per Method
- Don’t Use The ELSE Keyword
- Wrap All Primitives And Strings
- First Class Collections
- One Dot Per Line
- Don’t Abbreviate
- Keep All Entities Small
- No Classes With More Than Two Instance Variables
- No Getters/Setters/Properties

## Ressources
- [Domain Driven Design Quickly](https://www.infoq.com/minibooks/domain-driven-design-quickly/)
- [Conversation Patterns](https://www.infoq.com/minibooks/conversation-patterns/)
- [Analysis Patterns: Reusable Object Models
  ](https://www.oreilly.com/library/view/analysis-patterns-reusable/9780134271453/)
- [Software Design X-Rays - Adam Tornhill](https://pragprog.com/titles/atevol/software-design-x-rays/)
- [CodeScene](https://codescene.com)
