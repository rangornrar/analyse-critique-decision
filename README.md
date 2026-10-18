# Analyse critique et aide à la décision

Un skill en français pour confronter les hypothèses, comparer les options et formuler une recommandation argumentée, adaptée aux enjeux.

Il fournit une méthode de travail réutilisable à un assistant compatible avec les skills. Il ne modifie pas le modèle et ne garantit pas l'exactitude de ses réponses.

## Ce qu'il apporte

- Distinguer les faits vérifiés, les informations rapportées, les hypothèses et les inconnues.
- Examiner les points de vue pertinents : technique, exploitation, finances, humain, organisation ou autres selon le sujet.
- Tester l'objection la plus solide et défendre honnêtement l'alternative sérieuse.
- Comparer les coûts complets, risques, délais, dépendances et possibilités de retour en arrière.
- Éviter la validation automatique, les scores arbitraires et le faux équilibre entre opinion et preuve.
- Recommander une action concrète et préciser les conditions qui feraient changer d'avis.

L'analyse reste courte pour les décisions simples. Le skill n'est pas destiné aux corrections de texte, traductions ou questions factuelles isolées.

## Installation dans Codex local

### macOS ou Linux

Avec Git installé, exécuter dans un terminal :

```bash
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/rangornrar/analyse-critique-decision.git "$HOME/.agents/skills/analyse-critique-decision"
```

### Windows — PowerShell

Avec Git installé, exécuter :

```powershell
New-Item -ItemType Directory -Force -Path "$HOME/.agents/skills" | Out-Null
git clone https://github.com/rangornrar/analyse-critique-decision.git "$HOME/.agents/skills/analyse-critique-decision"
```

Ces commandes supposent que le dossier de destination n'existe pas encore. Si le skill n'apparaît pas, redémarrer Codex. Pour un usage limité à un projet, copier plutôt le dossier du skill dans `.agents/skills/analyse-critique-decision/` du projet.

### Mise à jour

```bash
git -C "$HOME/.agents/skills/analyse-critique-decision" pull --ff-only
```

Cette commande fonctionne aussi dans PowerShell. En cas de modifications locales ou de divergence, les examiner avant de les remplacer.

## Utilisation dans ChatGPT

L'accès aux skills, leur importation et leur synchronisation dépendent du compte, de l'espace de travail et de l'interface. La présence de ce dépôt public n'installe pas automatiquement le skill dans ChatGPT et ne le publie pas dans l'annuaire des plugins.

Dans une interface permettant de créer un skill avec un éditeur, reprendre le contenu de [SKILL.md](SKILL.md) et enregistrer le skill. Si l'importation est proposée, suivre le format demandé par cette interface. Ne pas supposer que l'archive ZIP du dépôt est directement importable partout.

Une fois le skill installé dans ChatGPT, le sélectionner avec `@` si cette commande est disponible. Dans Codex, utiliser `$analyse-critique-decision` ou le sélecteur de skills.

Sans installation, il reste possible de joindre le fichier SKILL.md à une conversation et de demander à l'assistant d'en appliquer la méthode pour cette conversation ; cela ne crée pas de skill persistant.

## Exemples de demandes

### Choix d'architecture IT

> Utilise $analyse-critique-decision pour comparer un monolithe modulaire et des microservices. Nous sommes cinq développeurs, avec peu de capacité d'exploitation et une livraison attendue dans six mois. Examine les compromis et ce qui justifierait de revoir le choix.

### Mettre un projet à l'épreuve

> Utilise $analyse-critique-decision pour examiner ce plan. Cherche son hypothèse la plus fragile, l'objection principale et un test peu coûteux avant de nous engager : [plan].

### Arbitrage professionnel

> Utilise $analyse-critique-decision pour comparer ces trois propositions. Mes priorités sont le délai, le coût total sur trois ans et la réversibilité : [propositions]. Signale les informations manquantes qui peuvent changer la décision.

### Décision simple

> Utilise $analyse-critique-decision pour m'aider à choisir entre ces deux options : [options et contraintes]. Réponds en dix lignes maximum.

## Fournir le bon contexte

Indiquer si possible : l'objectif, les options envisagées, les contraintes impératives, le budget, l'échéance et les inconnues. Ajouter les documents utiles ou demander une vérification des sources si le sujet le nécessite.

La réponse recherchée commence par une recommandation, explique les raisons et le compromis principal, puis propose une prochaine action. Un tableau ou une analyse plus longue ne sont utiles que si la complexité les justifie.

## Limites et vérification

- Les résultats dépendent du modèle, du contexte et des outils autorisés. Sans accès aux sources, une vérification externe peut être impossible ; le skill demande de le signaler.
- Examiner plusieurs angles avec un seul assistant ne constitue pas une expertise indépendante de plusieurs professionnels.
- Une méthode critique ne supprime pas les erreurs, les biais ou les informations manquantes.
- Une recommandation ne vaut pas autorisation d'agir à l'extérieur de la conversation.
- La validation initiale a couvert la structure du skill et un essai simple de comportement. Elle ne constitue pas une évaluation systématique de la qualité des décisions.

## Contenu du dépôt

| Fichier | Rôle |
| --- | --- |
| [SKILL.md](SKILL.md) | Instructions et critères de déclenchement |
| [agents/openai.yaml](agents/openai.yaml) | Métadonnées d'interface |
| [assets/icon.svg](assets/icon.svg) | Icône du skill |
| [LICENSE](LICENSE) | Licence MIT |

## Contribuer

Ouvrir une issue ou une pull request avec un cas concret, le comportement observé et le résultat souhaité. Utiliser des exemples anonymisés. Privilégier les améliorations qui renforcent la qualité des preuves et des arbitrages sans allonger inutilement les réponses.

## Documentation de référence

- [Créer et utiliser des skills — documentation OpenAI](https://learn.chatgpt.com/docs/build-skills)
- [Skills dans ChatGPT — aide OpenAI](https://help.openai.com/fr-fr/articles/20001066-skills-in-chatgpt)

Les interfaces et les règles d'installation peuvent évoluer ; vérifier ces références en cas de différence avec l'application utilisée.

## Licence

Distribué sous [licence MIT](LICENSE), autorisant l'utilisation, la modification et la redistribution, y compris commerciale, sous réserve de conserver les mentions de licence. Projet indépendant, sans affiliation ni approbation d'OpenAI.
