# Pipeline d'opportunités — premières pistes réelles

> Constitué par recherche web le 2026-08-19. Les sites officiels (mmsp.gov.ma, marocao.com, marchespublics.gov.ma) sont **inaccessibles depuis cet environnement d'exécution** (proxy réseau bloquant) : les informations ci-dessous viennent des résultats de recherche et des articles de presse cités, pas d'une lecture directe du dossier de candidature. **Chaque piste doit être vérifiée à la source par le porteur de projet avant toute action** (éligibilité exacte, statut ouvert/clos, date limite réelle).

## 1. AMI "Digital Lab" — Transition numérique de l'Éducation nationale (Maroc)

- **Porteur :** Ministère de l'Éducation Nationale, du Préscolaire et des Sports (MENPS), en lien avec le Ministère de la Transition Numérique et de la Réforme de l'Administration (MTNRA) et la CDG.
- **Objet :** Appel à manifestation d'intérêt auprès d'acteurs nationaux et internationaux de l'EdTech pour développer des solutions numériques répondant aux enjeux de la réforme éducative (remédiation scolaire, renforcement des compétences linguistiques, digitalisation des leçons, évaluation et suivi des acquis).
- **Pourquoi ça correspond :** recoupe directement l'offre 02 (ingénierie de formation) et 03 (automatisation/IA) du catalogue de services.
- **Statut :** annoncé en juillet 2024 dans le cadre de la feuille de route 2022-2026 du MENPS ; probablement structuré en cohortes/vagues successives — **à confirmer si un appel est actuellement ouvert**.
- **Sources :**
  - [Ministère de la Transition Numérique — communiqué de lancement](https://www.mmsp.gov.ma/fr/actualites/lancement-d%E2%80%99un-appel-%C3%A0-manifestation-d%E2%80%99int%C3%A9r%C3%AAt-pour-acc%C3%A9l%C3%A9rer-la-transition-num%C3%A9rique-de-l%E2%80%99%C3%A9ducation-nationale-au-maroc)
  - [Communiqué CDG (PDF)](https://www.cdg.ma/sites/default/files/CP_Digital_Lab_Vfr.pdf)
  - [La Quotidienne — reprise presse](https://laquotidienne.ma/article/economie/Maroc-transition-numerique-Education-nationale)
  - [AllAfrica — reprise presse](https://fr.allafrica.com/stories/202407230135.html)
- **Action immédiate suggérée :** contacter directement le Digital Lab (coordonnées sur le site du MENPS ou de la CDG) pour demander si une cohorte est ouverte et quelles sont les modalités actuelles de candidature.

## 2. OFPPT — Plan d'action 2026 (ingénierie de programmes de formation professionnelle)

- **Porteur :** OFPPT (Office de la Formation Professionnelle et de la Promotion du Travail).
- **Objet :** Budget 2026 de 6,31 milliards MAD incluant le développement de 65 programmes de formation (43 nouveaux, 22 restructurés) et la digitalisation des processus (dématérialisation des diplômes notamment). Priorités affichées : économie verte, cybersécurité, gaming, intelligence artificielle.
- **Pourquoi ça correspond :** l'OFPPT sous-traite régulièrement la conception de référentiels et l'ingénierie pédagogique à des prestataires externes via marchés publics — offre 02 du catalogue.
- **Statut :** plan d'action confirmé pour 2026 ; **les marchés publics associés doivent être recherchés individuellement** sur le portail marchespublics.gov.ma (mots-clés : "ingénierie pédagogique OFPPT", "référentiel de formation", "digitalisation OFPPT").
- **Sources :**
  - [LesEco.ma — plan d'action 2026 OFPPT](https://leseco.ma/business/ofppt-le-plan-2026-accelere-la-transformation-de-la-formation-professionnelle.html)
  - [DRH.ma — détail budgétaire](https://drh.ma/ofppt-un-plan-daction-2026-a-631-milliards-de-dirhams-pour-adapter-la-formation-professionnelle-aux-nouveaux-metiers/)
- **Action immédiate suggérée :** créer une alerte de veille (cf. `n8n-workflows/veille-appels-offres.json`) sur "OFPPT" + "ingénierie pédagogique"/"référentiel"/"digitalisation".

## 3. Portails d'appels d'offres à surveiller en continu

- [marocao.com/formations](https://marocao.com/formations) — agrégateur d'AO marocains, section formation (accès direct bloqué depuis cet environnement, à consulter manuellement).
- [j360.info — AO Maroc, enseignement/formations](https://www.j360.info/appels-d-offres/afrique/maroc/?act=enseignement-formations)
- Portail officiel : marchespublics.gov.ma (marchés publics marocains, recherche par mot-clé et secteur).

## 4. Pistes hors Maroc / bailleurs (à qualifier plus tard)

- Appels à manifestation d'intérêt liés à l'IA et à l'éducation en Afrique francophone (ex. programme Niyel, orienté sociétés civiles — **probablement non éligible pour un cabinet de conseil à but lucratif**, à vérifier).
- [Appel à projets 2026 "L'innovation pour tous" — France au Maroc](https://asso.lafranceaumaroc.org/appel-a-projets-2026-innovation-pour-tous/) — numérique/inclusion, éligibilité à vérifier.

## Prochaine étape concrète

1. Vérifier l'éligibilité et le statut réel de la piste n°1 (Digital Lab) — c'est la plus alignée avec le positionnement du cabinet.
2. Dès qu'un appel confirmé et ouvert est identifié, dupliquer [`kit-appels-offres/memoire-technique-template.md`](./kit-appels-offres/memoire-technique-template.md) pour rédiger une réponse ciblée.
3. Activer le workflow n8n de veille avec des alertes Google Alerts sur "OFPPT ingénierie pédagogique", "Digital Lab MENPS", "marché public formation digitale Maroc".

---

**Limite importante à noter :** je n'ai pas pu accéder directement aux sites mmsp.gov.ma et marocao.com depuis cet environnement (blocage réseau) — ces pistes viennent de résultats de recherche et n'ont pas été vérifiées à la source. Aller plus loin (confirmer l'éligibilité exacte, obtenir le dossier de candidature, déposer un dossier, signer un contrat) nécessite une action humaine directe : ce sont des démarches que je ne peux pas accomplir à la place du porteur de projet, faute d'accès et d'existence légale du cabinet à ce stade.
