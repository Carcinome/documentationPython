**PEP 8 Python**
================

**2.1 Convention de noms des variables**
----------------------------------------

Les variables suivent une des conventions de noms suivantes selon si elles appartiennent aux variables dites "classiques" ou aux variables constantes. 


**2.1.1 Variables**
^^^^^^^^^^^^^^^^^^^

Les variables "classiques" s'écrivent en minuscules avec des underscores (convention *snake_case*) :

.. code-block:: python

    name = "Lucas"
    fuel_level = 100
    famous_singers = ["Céline Dion", "Eminem", "Charles Aznavour"]


**2.1.2 Variables constantes**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Les variables constantes s'écrivent en majuscules avec des underscores :

.. code-block:: python

    DAYS_PER_WEEK = 7
    PERSONNAL_EMAIL = "examplemail@email.gov"


**2.2 Convention de noms des classes**
--------------------------------------

**2.2.1 Classes**
^^^^^^^^^^^^^^^^^

Les noms de classes sont écrits avec une majuscule au début de chaque mot, sans ponctuation (convention *CapitalCase*) :

.. code-block:: python

    class MangasStore:
        pass

    class VideoGames:
        pass


**2.3 Convention de noms des modules**
--------------------------------------

**2.3.1 Modules**
^^^^^^^^^^^^^^^^^

Les noms des modules sont à écrire en minuscules en évitant au maximum les underscores :

.. code-block:: python

    import os
    import sys
    import pandas

**2.4 Formalisme d'écriture des commentaires**
----------------------------------------------

**2.4.1 Commentaires**
^^^^^^^^^^^^^^^^^^^^^^

- Les commentaires sont à écrire sous forme de phrase complète, en anglais si possible sauf si l'équipe de développement préfère une autre langue.
- Il est fortement recommandé de ne pas contredire le code en utilisant les commentaires. 
- Les commentaires doivent impérativement être mis à jour lorsque le code change.
- Il est recommandé de ne pas mettre le commentaire sur la même ligne que le code. 
- Un seul espace entre le `#` et le code est requis. 
- Il faut utiliser le même niveau d'indentation que la ligne de code qui suit. 

.. code-block:: python 

    # Commentaire correctement formulé 
    def foo(arg):
        # Commentaire correctement formulé
        pass
    
        # Commentaire mal formulé
    def foo(arg):
    # Commentaire mal formulé
        pass
    

**2.4.2 Chaînes de documentation**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Plus communément appellées *docstrings*, les chaînes de documentation sont des commentaires spéciaux à rédiger au début d'une fonction, d'une classe ou d'un module. 
On les utilise pour la documentation. Elles permettent aussi aux outils automatisés d'accéder au texte. 
Tout comme les commentaires cités plus haut, les doctrings sont à rédiger de préférence en anglais. 
Il est recommandé contrairement aux commentaires d'en utiliser à profusion, même pour une courte description. 

.. code-block:: python

    def multiply(first, second=1):
        """Multiplie deux nombres. 

        Arguments:
            first -- le multiplicande
            second -- le multiplicateur (par défaut, 1)
        """
        return first * second

    print(multiply(13, 77))
    print(multiply.__doc__)

.. note::

    Les docstrings en début de fonction ou de classe sont spéciales, on peut y accéder en utilisant l'attribut `__doc__`.


**2.5 Convention d'écriture de code**
-------------------------------------

**2.5.1 Indentation**
^^^^^^^^^^^^^^^^^^^^^

Il est recommandé d'utiliser **4 espaces** ou une **tabulation** pour éviter les erreurs d'indentation. 

- Un seul espace autour des opérateurs d'affectation et des opérateurs logiques. La seule exception intervient lorsqu'on fixe des valeurs par défaut en paramètres de fonctions et methodes (`second=1`, vu plus haut).

.. code-block:: python

    # Opérateur d'affectation
    is_little = "little" in sanctuary

    # Opérateur logique
    max_places < 5

- Ne jamais mettre d'espaces tout de suite à l'intérieur de parenthèses ou de crochets.

.. code-block:: python

    # Correct
    (expression)
    [0]

    # Incorrect
    ( expression )
    [ 0 ]

- Ne pas laisser d'espace entre une fonction et ses arguments. 

.. code-block:: python

    print(f"Nous avons protégés ces animaux : {protected}")

- Laisser un espace entre `if` et toute parenthèse. La même règle s'applique pour `for`. Cela maintient la cohérence avec les cas de figure dans lesquels il n'y a pas de parenthèses. 


**2.5.2 Sauts de ligne**
^^^^^^^^^^^^^^^^^^^^^^^^

Les sauts de ligne sont à utiliser pour regrouper les lignes de code qui vont ensemble (à la manière de paragraphes). En dehors de cela, il est recommandé de ne pas sauter de ligne.

- Avant une définition de classe ou une définition de fonction, il faut sauter deux lignes. 
- Avant la définition d'une méthode au sein d'une classe, un seul saut de ligne est à prévoir. 

.. code-block:: python

    name = "Clément"


    def multiply(first, second=1):
        """Multiplie deux nombres. 

        Arguments:
            first -- le multiplicande
            second -- le multiplicateur (par défaut, 1)
        """
        return first * second

    print(multiply(13, 77))
    print(multiply.__doc__)


    class ToolBox:

    """Boite à outils."""

    def __init__(self):
        """Initialise les outils."""
        self.tools = []

    def add_tool(self, tool):
        """Ajoute un outil."""
        self.tools.append(tool)

    def remove_tool(self, tool):
        """Enleve un outil."""
        index = self.tools.index(tool)
        del self.tools[index]

def function_with_a_rather_long_name(parameter_number_1, parameter_number_2,
        parameter_number_3):
        my_function(parameter_number_1)
        return parameter_number_2
^^^^^^^^^^^^^^^^^^^^^^^^

- Concernant la longueur maximum d'une ligne de code, la PEP 8 suggère de limiter le nombre de caractères à **79**.
- Pour écrire des expressions sans dépasser cette limite suggérée, on doit les écrire sur plusieurs lignes. 

.. code-block:: python

    # Exemple d'écriture d'expressions incorrect
    def function_with_a_rather_long_name(parameter_number_1, parameter_number_2,
        parameter_number_3):
        my_function(parameter_number_1)
        return parameter_number_2
    
    # On peut aligner les paramètres sur la verticale
    def function_with_a_rather_long_name(parameter_number_1, parameter_number_2,
                                         parameter_number_3):
        my_function(parameter_number_1)
        return parameter_number_2

    # On peut procéder avec un paramètre par ligne
    def function_with_a_rather_long_name(parameter_number_1, 
                                         parameter_number_2,
                                         parameter_number_3):
        my_function(parameter_number_1)
        return parameter_number_2

    # Ou encore, avec un paramètre par ligne et la parenthèse au niveau de l'indentation de la fonction
    def function_with_a_rather_long_name(
        parameter_number_1,
        parameter_number_2,
        parameter_number_3
    ):
        my_function(parameter_number_1)
        return parameter_number_2

- Il est possible de découper de longues chaînes de caractères avec la manière ci-dessous, Python les interprétera comme une seule chaîne de caractères lors de l'exécution du code. 

.. code-block:: python

    ultra_long_password = ( 
        "dfsghfghgfh(bvxdsfsglgjhsdghgt_y(çp_ghstrisdhgdhg"
        "lfgàjçdjfgdkgbslgfgbixfugfgblfdgkvbxcvxvqufsdvfsd"
        "dfghffidkgljfg-_è-çàghjdgdlbfhgdflhgkdnmbszuzhgpc"
        "dkdky-çèàytjhfmghompfddfgjfo-çjjhjsbéj&lksldnflde"
    )


**2.6 formatage du code**
-------------------------

**2.6.1 linters**
^^^^^^^^^^^^^^^^^

Les linters permettent d'éviter de rencontrer les problèmes liés au non-respect de la convention PEP 8.

Certains linters sont disponibles en ligne et d'autres sont directement intégrés au IDE, mais il reste préférable d'installer les packages `Flake8` et `Black` directement dans votre environnement Python.

.. code-block:: python

    pip install flake8
    pip install black

Une fois les packages installés, `flake8` et `black` peuvent être lancés dans la console Python en précisant le chemin d'accès du fichier concerné pour procéder 
à la vérification du respect des normes PEP 8 (flake8) et à la bonne mise en forme du code (black). 

.. code-block:: python

    flake8 /code_python/codeAcorriger.py
    black /code_python/codeAcorriger.py


**2.7 Patterns**
----------------

**2.7.1 Design pattern Constant**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Le design pattern Constant est un modèle de simple qui n'affecte qu'une seule valeur dans le code. 
Il préconise de mettre des mots sur des valeurs brutes afin d'éviter le problème de *nombres magiques*, constantes numériques non-nommées et très compliquées à maintenir. 
Par exemple : 

.. code-block:: python

    # Mauvaise syntaxe
    SEIZE = 16

    # Bonne syntaxe
    NOMBRE_DE_BITS = 16

Cette syntaxe permet d'éviter les bugs de correction et modification, de faciliter la maintenance collaborative du code et de réduire au maximum le code superflu et les répétitions. 


**2.7.2 Design pattern Decorateur**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Ce design à pour but d'ajouter dynamiquement des fonctionnalités à un objet, sans modification de sa structure. Il est comparable à une fonction prennant en argument des fonctions et ce en ajoutant des fonctionnalités avant et après son exécution. 
Cela permet d'ajouter des fonctionnalités à un objet sans modifier son code de manière directe.

Voici ci-dessous poyur un exemple concret : 

.. code-block:: python

     from abc import ABC, abstractmethod

     class Cocktail(ABC):
        @abstractmethod
        def get_description(self) -> str:
            pass

        @abstractmethod
        def get_cout(self) -> float:
            pass
    
    class Mojito(Cocktail):
        def get_description(self) -> str:
            return "Mojito"

        def get_cout(self) -> float:
            return 10.0
    
    class DecorateurCocktail(Cocktail):
        def __init__(self, cocktail: Cocktail):
            self._Cocktail = Cocktail
    
    class Fraise(DecorateurCocktail):
        def get_description(self) -> str:
            return self._Cocktail.get_description + ", fraise"
        
        def get_cout(self) -> float:
            return self._Cocktail.get_cout + 0.7
    
    class Sucre(DecorateurCocktail):
        def get_description(self) -> str:
            return self._Cocktail.get_description + ", sucre"

        def get_cout(self) -> float:
            return self._Cocktail.get_cout + 1.5

    Cocktail = Mojito()

    Cocktail = fraise(Cocktail)

    Cocktail = sucre(Cocktail)

    print(Cocktail.get_description()) # Mojito, fraise, sucre
    print(Cocktail.get_cout()) # 10.0 + 0.7 + 1.5 = 12.2


**2.7.3 Pattern d'architecture MVC**
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^


