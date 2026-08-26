# Sécurité et confidentialité

## Frontière de publication

Le code source du portfolio reste dans un dépôt privé. Ce dépôt décrit
l'architecture logique du système.

Ne sont publiés nulle part : secrets et variables d'environnement, clés d'API,
mots de passe, configuration réelle du serveur, identifiants, adresses internes,
chemins d'exploitation, journaux, données de production.

Les projets professionnels décrits sur le site ont été menés dans un système
d'information hospitalier. La règle y est écrite : les problèmes rencontrés, les
solutions développées et leurs résultats sont documentés ; les éléments
permettant d'identifier ou de cartographier l'environnement interne ne le sont
pas.

Les métriques publiées sont **agrégées**. Un nombre d'interventions se publie ;
la liste des applications concernées, non.

## Secrets

Aucun secret dans le dépôt, dans l'historique ou dans l'image construite. Les
valeurs sensibles sont fournies à l'exécution par l'environnement du conteneur.

## Données personnelles

Le site ne dépose aucun cookie et n'utilise aucun service de mesure d'audience
tiers. Ni compte, ni formulaire, ni collecte volontaire d'information.

La mesure d'audience est calculée depuis les journaux du serveur web. L'adresse
est réduite à son réseau avant traitement, puis transformée en empreinte à
l'aide d'une clé secrète ; l'adresse complète n'est pas conservée dans la base
de mesure.

**Ce qui n'est pas affirmé.** Une empreinte salée n'est pas une donnée anonyme :
l'irréversibilité tient au secret de la clé, pas aux mathématiques. La
distinction entre pseudonymisation et anonymisation compte, et la page légale du
site décrit le traitement sans promettre un état juridique que le mécanisme ne
garantit pas.

## Limitation des abus

L'assistant est borné par une empreinte calculée selon le même procédé, par une
cadence maximale et par un plafond de dépense quotidien.

Les valeurs de ces plafonds ne sont pas toutes publiées : en publier certaines
donnerait le mode d'emploi du contournement. Le règlement demande la finalité,
pas la recette.

Le dispositif ne rend pas l'abus impossible, il le rend coûteux. Le rempart
final reste un budget borné en euros.

## Exposition

HTTPS uniquement, certificats gérés par le reverse proxy. L'application n'est
pas exposée directement.
