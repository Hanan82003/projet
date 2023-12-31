nom:belghali
prénom:hanane
groupe:02

#projet
projet système d'exploitation
# Multiplication des Matrices


Q1: Quelles sont les structures de données à utiliser ?

A1: Dans le contexte d'un programme de multiplication de matrices avec un modèle producteur/consommateur,
les principales structures de données utilisées sont les matrices B, C, A et T. Ces matrices sont 
généralement représentées sous forme de tableaux bidimensionnels.
Matrice B (n1 x m1)
Matrice C (n2 x m2)
Matrice A (n1 x m2) : Matrice résultante de la multiplication
Matrice T (n1 x m2) : Tampon pour les résultats intermédiaires


Q2: Comment allez-vous protéger l'accès à ces données?

Pour protéger l'accès aux données partagées entre les threads, vous utiliserez des mécanismes de synchronisation. 
Dans le code fourni précédemment, les principaux mécanismes de synchronisation sont un mutex (pthread_mutex_t mutex)
et deux sémaphores (sem_t empty et sem_t full).
1)Mutex (pthread_mutex_t) : Le mutex est utilisé pour assurer l'exclusion mutuelle, ce qui signifie qu'un seul 
thread peut accéder à la section critique à la fois.
2)Sémaphores (sem_t empty) : Le sémaphore est utilisé pour gérer le nombre de places libres (empty) dans le tampon T.
3)Sémaphores (sem_t full) : Le sémaphore est utilisé pour gérer le nombre de places occupées (full) dans le tampon T.


Q3: Quels sont les risques?

A3: L'utilisation de threads pour exécuter des tâches simultanées dans un programme peut entraîner divers risques 
liés à la concurrence. Voici quelques-uns des risques courants associés à la programmation multithread :
1)Condition de course (Race Condition) : Il s'agit d'une situation où plusieurs threads accèdent simultanément à 
des données partagées et tentent de les modifier, ce qui peut entraîner des résultats imprévisibles. 
2)Deadlock : Un deadlock se produit lorsque deux ou plusieurs threads attendent indéfiniment que l'autre 
libère une ressource. Cela peut se produire si les mécanismes de synchronisation ne sont pas correctement conçus.
3)Starvation : La starvation se produit lorsqu'un thread est incapable de faire progresser son travail en 
raison de problèmes d'ordonnancement ou de synchronisation.
4)Problèmes de performance : Si la synchronisation n'est pas correctement équilibrée, cela peut entraîner des inefficacités.
5)Priorité des threads : La gestion incorrecte des priorités des threads peut entraîner des situations où certains 
threads ont une priorité disproportionnée par rapport à d'autres.
6)Complexité accrue : La programmation multithread introduit une complexité supplémentaire dans la gestion des threads, 
des données partagées et de la synchronisation.

