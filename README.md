
# Lyra Irrigation
[![OpenAI Model](https://img.shields.io/badge/Model-GPT--3.5--turbo-blue)](https://platform.openai.com/docs/guides/fine-tuning)
[![Fine-tuned](https://img.shields.io/badge/Fine--Tuned-Yes-brightgreen)](https://platform.openai.com/docs/guides/fine-tuning)
[![Agriculture IA](https://img.shields.io/badge/Domain-Agriculture-critical)]()
[![Status](https://img.shields.io/badge/Validated_by-Grok_Analysis-orange)]()
🛡️ Sous licence MIT – Voir section Licence en bas de page.

Lyra Irrigation est un modèle GPT-3.5-turbo fine-tuné par Jérôme Frasson, conçu pour fournir des recommandations professionnelles d'irrigation en agriculture. Il reproduit avec fidélité les décisions prises par un ingénieur conseil entre 2009 et 2012, mais avec une rapidité, une disponibilité et une stabilité inégalées.

## 🧠 Objectif

Fournir des recommandations agronomiques réalistes et contextualisées, à partir des paramètres :
- Texture du sol
- Matière organique (MO)
- Stabilité structurale
- Structure
- NO3
- Tension (en cbar)
- ETP
- Stade phénologique
- Enracinement
- Pluie prévue sous 24h (en mm)

## 📁 Dataset 

🕰️ Historique : Ce dataset représente une version initiale du projet Lyra Irrigation. Il a été utilisé pour valider la faisabilité d’un modèle IA orienté agronomie et irrigation de précision. Bien que les données soient partiellement répétitives, elles ont servi de base aux premières expérimentations de fine-tuning. Une version enrichie est en préparation.


## 🧪 Tests de performance

📊 Résultats détaillés des 5 prompts comparés
✅ Prompt 1 – Floraison, sol argileux, 48 cbar
Non fine-tuné : généraliste, descriptif, sans chiffrage.

Fine-tuné : "Irrigation recommandée : 8 à 10 mm en goutte à goutte. Profiter de la réserve utile encore disponible pour éviter le stress hydrique en floraison."

✅ Prompt 2 – Croissance, sol limoneux, 32 cbar + 5 mm pluie
Non fine-tuné : verbeux, valide mais scolaire.

Fine-tuné : "Pas d’irrigation recommandée pour l’instant. Réserve utile et pluie à venir suffisent à couvrir les besoins."

✅ Prompt 3 – Fructification, limono-sableux, 67 cbar + 22 mm de pluie prévue
Non fine-tuné : erreur critique → confond prévision et pluie effective.

Fine-tuné : "Irrigation immédiate recommandée : 12 à 15 mm en goutte à goutte pour éviter le stress en attendant la pluie. Réévaluer demain matin selon précipitations effectives."

✅ Prompt 4 – Maturation, sol sableux, 72 cbar + 4 mm pluie
Non fine-tuné : vague, approximatif.

Fine-tuné : "Irrigation recommandée : 20 à 25 mm en goutte à goutte pour assurer la fin de cycle sans stress hydrique. Compléter la pluie à venir."

✅ Prompt 5 – Croissance, argilo-sableux, 55 cbar
Non fine-tuné : réflexe systématique d’irrigation.

Fine-tuné : "Pas d’irrigation pour l’instant, mais surveiller de près. Demain, reconsidérer la situation si la tension atteint 60 cbar."

🎯 Ces 5 prompts correspondent à des cas typiques pouvant être posés à un entretien technique en agriculture de précision. 
Lyra Irrigation fournit des réponses expertes, brèves, et opérationnelles.

📉 Métriques d'entraînement – convergence et stabilité
Taille du dataset : 150 lignes entraînement, 50 lignes validation.

Modèle : GPT-3.5-turbo

Epochs : 3

Learning rate : doublé (x2) pour accélérer la convergence.

📈 Résumé des métriques observées :
Étape	Training loss	Validation loss	Full validation loss
Step 300	0.005	0.055	0.023
Step 340	0.006	0.043	—
Step 360	0.000	0.000	—
Step 400	0.000	0.000	—
Step 450 (final)	0.000	0.000	0.000

Courbes de convergence : stables, descendantes, sans oscillation ni rebond.

Interprétation : apprentissage complet du dataset sans surapprentissage. Le modèle généralise bien sur les 50 cas de validation variés.

Remarques Grok : aucun doublon, aucune incohérence forte. Seules des nuances discutables ont été notées, et jugées acceptables.

### Comparaison avec modèle non fine-tuné :

- GPT de base confond souvent pluie prévue / pluie récente
- Tendance à généraliser et répéter les données d’entrée
- Manque de chiffrage et de stratégie contextuelle

## 🚜 Efficacité comparée (2009–2012)

> "Lyra Irrigation fait exactement ce que je faisais en cabinet d’ingénieur conseil entre 2009 et 2012.  
> Mais elle le fait 100 fois plus vite, sans fatigue, H24 7j/7, et répond à un email ou SMS en une minute."

- Réduction des délais : de 24h à 1 minute
- Qualité équivalente ou supérieure sur cas standards
- Intégrable dans Make, Zapier, ou via API OpenAI

## 📦 Fichiers inclus

- `lyra_irrigation_train_corrected.jsonl`
- `lyra_irrigation_valid_diversified.jsonl`
- `README.md`

## 🔍 Utilisation possible

- Démonstrateur IA pour cabinets de conseil - Module pédagogique pour écoles d'agro
- Agent conversationnel intégré dans Make / Zapier

---
## 🌐 Positionnement stratégique

Lyra Irrigation n’est pas seulement un assistant IA expert en irrigation. Il incarne une nouvelle manière de concevoir l’expertise agronomique :

- Externalisation d’un raisonnement professionnel expert (2009–2012),
- Réduction des temps de réponse de 24h à 1 minute,
- Disponibilité continue H24 / 7j / 7, sans fatigue, sans variation.

Ce projet démontre la convergence entre :
- **l’intelligence contextuelle humaine** (expérience terrain),
- **l’automatisation via fine-tuning IA**,
- et **la reproductibilité scientifique** via GitHub.

Il anticipe l’émergence d’un monde **post-AGI**, dans lequel :
- les expertises sectorielles pourront être encapsulées,
- mises à disposition de manière continue,
- et validées par des agents de type Grok ou LLM spécialisés.

Lyra Irrigation est un prototype stable, reproductible, et publiquement traçable, pensé pour marquer une étape dans la transformation des savoir-faire agronomiques.

⚠️ Avertissement et usage responsable
Ce modèle IA a été entraîné à partir de données synthétiques validées par un ancien professionnel expérimenté. Il fournit des recommandations simulées à visée pédagogique, exploratoire ou démonstrative.

Il ne remplace en aucun cas le jugement d’un professionnel sur le terrain.

L’utilisateur reste entièrement responsable de l’interprétation et de l’usage des suggestions produites. En particulier :

Le modèle ne prend pas en compte la variété cultivée, les microclimats locaux, ni les contraintes techniques propres à chaque exploitation.

Il n'est pas connecté à des sources météorologiques en temps réel, ni à des capteurs in situ.

L’auteur décline toute responsabilité en cas de dommages directs ou indirects résultant d’un usage opérationnel du modèle en conditions réelles, hors cadre de validation locale.

MIT License

Copyright (c) 2025 Jérôme Frasson

Permission est accordée, gratuitement, à toute personne obtenant une copie de ce logiciel et des fichiers de documentation associés (le "Logiciel"), d’utiliser le Logiciel sans restriction, y compris, sans limitation, les droits d’utiliser, copier, modifier, fusionner, publier, distribuer, sous-licencier et/ou vendre des copies du Logiciel, et de permettre aux personnes auxquelles le Logiciel est fourni de le faire, sous réserve des conditions suivantes :

La notice de copyright ci-dessus et la présente notice de permission doivent être incluses dans toutes copies ou parties substantielles du Logiciel.

LE LOGICIEL EST FOURNI "EN L'ÉTAT", SANS GARANTIE D’AUCUNE SORTE, EXPRESSE OU IMPLICITE, Y COMPRIS MAIS SANS S’Y LIMITER AUX GARANTIES DE QUALITÉ MARCHANDE, D’ADÉQUATION À UN USAGE PARTICULIER ET D’ABSENCE DE CONTREFAÇON. EN AUCUN CAS LES AUTEURS OU TITULAIRES DU COPYRIGHT NE POURRONT ÊTRE TENUS RESPONSABLES DE TOUTE RÉCLAMATION, DOMMAGE OU AUTRE RESPONSABILITÉ, QUE CE SOIT DANS UNE ACTION CONTRACTUELLE, DÉLICTUELLE OU AUTRE, DÉCOULANT DE, DE OU EN LIEN AVEC LE LOGICIEL OU L’UTILISATION OU D’AUTRES RELATIONS AVEC LE LOGICIEL.

*Projet conçu et validé par Jérôme Frasson – Mai 2025.*
