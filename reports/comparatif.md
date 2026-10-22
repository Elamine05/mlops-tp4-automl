
# Comparatif des approches - projet fraude (TP04)

| Approche | F1 test | Temps humain | Temps machine | Cout estime (source, date) | Explicabilite | Export / reversibilite |
|---|---|---|---|---|---|---|
| Logistique (ref.) | 0.7407 | Non mesure | 0.10 s | 0 (poste local) | Maximale | Total |
| Manuel (TP2) | 0.8669 | Non mesure | 1.69 s | 0 (poste local) | Moyenne/Bonne | Total |
| FLAML 60 s (XGBoost) | 0.8582 | Non mesure | 60.1 s | 0 (poste local) | Moyenne/Basse | Total |
| Vertex AI AutoML | non mesure | Configuration cloud (non mesuree) | Non mesure | Noeud-heure + deploiement ; exemple officiel d'atelier : environ 22 USD (Google, 22/10/2026) | Bonne | Export possible sous conditions ; reversibilite partielle |
| SageMaker Autopilot | non mesure | Configuration cloud (non mesuree) | Non mesure | Instance-heure + stockage ; exemple ml.m5.xlarge : 0,23 USD/h (AWS, 22/10/2026) | Bonne | Artefacts et notebooks exportables ; reversibilite partielle |
| Azure Automated ML | non mesure | Configuration cloud (non mesuree) | Non mesure | Calcul VM selon region et duree + services annexes ; tarif variable (Microsoft, 22/10/2026) | Bonne | Export PKL et ONNX selon compatibilite ; reversibilite partielle |

## Commentaire (5 lignes)

1. La regression logistique (F1 = 0.7407, 0.10 s) convient pour etablir rapidement une reference simple, peu couteuse et facilement interpretable.
2. Le reglage manuel Random Forest (F1 = 0.8669, 1.69 s) est preferable lorsqu'on souhaite maitriser les hyperparametres et obtenir de bonnes performances sur ce jeu de donnees.
3. FLAML 60 s (F1 = 0.8582, 60.1 s) permet d'automatiser la recherche et la comparaison de plusieurs familles de modeles, meme si son score reste ici inferieur au reglage manuel.
4. Vertex AI AutoML et SageMaker Autopilot sont adaptes aux projets necessitant une infrastructure cloud geree, une automatisation des experimentations et des ressources de calcul extensibles.
5. Azure Automated ML convient particulierement aux organisations utilisant deja Azure ; pour chaque plateforme cloud, le cout, l'explicabilite et la reversibilite doivent etre pris en compte.

## Sources officielles (consultation : 22/10/2026)

- Google Vertex AI : https://docs.cloud.google.com/vertex-ai/docs/tutorials/tabular-automl/dataset-train
- Google, exemple de cout : https://codelabs.developers.google.com/vertex-automl-tabular
- Google, tarification : https://cloud.google.com/vertex-ai/pricing
- AWS Autopilot : https://docs.aws.amazon.com/sagemaker/latest/dg/autopilot-automate-model-development.html
- AWS, tarification : https://aws.amazon.com/sagemaker/ai/pricing/
- Azure Automated ML : https://learn.microsoft.com/en-us/azure/machine-learning/concept-automated-ml?view=azureml-api-2
- Azure, tarification : https://azure.microsoft.com/en-us/pricing/details/machine-learning/
