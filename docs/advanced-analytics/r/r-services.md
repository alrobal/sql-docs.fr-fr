---
title: "Services d’apprentissage Microsoft | Documents Microsoft"
ms.custom:
- SQL2016_New_Updated
ms.date: 07/31/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- r-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 341e80f5-3b59-4122-bbaa-969d7904297d
caps.latest.revision: 23
author: jeannt
ms.author: jeannt
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 60272ce672c0a32738b0084ea86f8907ec7fc0a5
ms.openlocfilehash: ae040907dcf767f7b1f95922fa1fed35cc14efc9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/06/2017

---
# <a name="microsoft-machine-learning-services"></a>Services Microsoft Machine Learning

Microsoft Machine Learning Services vise à fournir une plateforme extensible et évolutive pour l’intégration des outils et les tâches d’apprentissage automatique avec les applications qui utilisent des services de machine learning. La plate-forme doit répondre aux besoins de tous les utilisateurs impliqués dans le processus de l’analytique et le développement de données à partir des chercheurs de données, pour les architectes et les administrateurs de base de données.

Principaux avantages :

+ Analytique évolutive
+ Plusieurs plateformes et les contextes de calcul pour les solutions « écrire une seule fois, n’importe où déployer »
+ Permet d’éviter le déplacement des données et risque de données en rassemblant analytique aux données
+ Les chercheurs de données peuvent choisir leurs propres outils et les langues
+ Intègre les meilleures fonctionnalités d’open source avec les fonctionnalités d’entreprise de Microsoft
+ Administration simplifiée
+ Facile à déployer et utiliser des modèles prédictifs

## <a name="in-database-analytics-with-sql-server"></a>Dans la base de données analytique avec SQL Server

Dans SQL Server 2016, Microsoft a lancé deux plateformes serveur permettant d’intégrer le langage R open source populaires avec les applications d’entreprise :

+ **SQL Server R Services (dans la base de données)**, pour l’intégration avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]
+ **Microsoft R Server**, pour les déploiements de R au niveau de l’entreprise sur les serveurs Windows et Linux

Dans SQL Server 2017, le nom a été modifié pour refléter la prise en charge pour le langage Python populaire.

+ **SQL Server Machine Learning Services (de-de base de données)** prend en charge de R et Python pour la base de données analytique.
+ **Microsoft Machine Learning Server** prend en charge les déploiements de R et Python sur les serveurs Windows, avec une expansion à d’autres plateformes prises en charge prévue pour la liaison tardive 2017.

### <a name="benefits"></a>Avantages

Microsoft Machine Learning Services met le calcul pour les données en permettant à R à exécuter sur le même ordinateur que la base de données. Il inclut le service Launchpad de confiance, qui s’exécute en dehors du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] traiter et communique de façon sécurisée avec le runtime R ou Python.

À l’aide de la Machine Learning Services SQL Server, vous pouvez effectuer l’apprentissage des modèles, générer des graphiques, effectuer le calcul de score et déplacer facilement des données entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et R ou Python.

Chercheurs de données qui testent et développent des solutions peuvent envoyer des scripts à partir d’un ordinateur de développement à distance pour exécuter du code en toute sécurité sur le serveur, ou ils peuvent déployer des solutions terminées sur SQL Server en incorporant le code machine learning dans les procédures stockées SQL.

Lorsque vous installez d’apprentissage pour SQL Server, vous obtenez une distribution de R open source ou de langage Python, ainsi que les bibliothèques R et Python évolutives, fournis par Microsoft. Le moteur de base de données SQL Server inclut également les nouveaux composants sont conçues pour renforcer la connectivité et de garantir plus rapidement, plus une communication sécurisée avec les langues externes tels que R ou Python.

### <a name="where-to-get-it"></a>Où l’obtenir

Pour commencer, consultez ces ressources :

+ [SQL Server R Services](sql-server-r-services.md)
+ [Services SQL Server Python](../python/sql-server-python-services.md)
+ [Didacticiels d’apprentissage](../tutorials/machine-learning-services-tutorials.md)

> [!NOTE]
> Prise en charge de Python est fournie uniquement dans SQL Server 2017. 

## <a name="machine-learning-server-standalone-and-microsoft-r-server-standalone"></a>Apprentissage Server (autonome) et Microsoft R Server (autonome)

Ce système de serveur autonome prend en charge des solutions R évolutives et distribuées sur plusieurs plateformes et à l’aide de plusieurs sources de données d’entreprise, tels que Linux et HD Insight. Si vous n’avez pas besoin de s’intégrer avec SQL Server, vous pouvez installer R Server pour permettre le développement rapide, le déploiement et une Opérationnalisation rapides des solutions d’apprentissage. Vous pouvez également utiliser les programmes d’installation de R Server pour mettre à niveau les composants de R associés à une instance de SQL Server et d’obtenir la dernière version de R.

Si vous installez Microsoft Machine Learning Server à l’aide du programme d’installation de SQL Server 2017, vous pouvez également déployer et utiliser les applications Python.

Pour plus d’informations, consultez [Microsoft R Server](https://docs.microsoft.com/r-server/index).

## <a name="related-technologies"></a>Technologies connexes

Microsoft prend en charge étendue des écosystèmes d’apprentissage machine, y compris les outils, les fournisseurs, des packages R et Python améliorés, un développement cloud et plateforme de services et un environnement de développement intégré.

### <a name="r-tools-for-visual-studio"></a>Outils R pour Visual Studio

Visual Studio fournit un environnement de développement complet pour le langage R. Le plug-in inclut un éditeur, une fenêtre interactive, un outil de traçage, un débogueur et plus encore. Vous pouvez utiliser les langages .NET à partir de R ou appeler R à partir de .NET au moyen de bibliothèques open source comme R.NET et rClr.

Visual Studio propose également un excellent environnement de développement Python. Il n’existe aucun moyen plus facile de travailler avec les langues d’apprentissage machine tout en continuant à accéder aux outils de développement de base de données SQL.

Pour plus d'informations, consultez :

+ [Outils R pour Visual Studio](https://www.visualstudio.com/vs/rtvs/)
+ [Python - Visual Studio](https://www.visualstudio.com/vs/python/)

### <a name="azure-machine-learning"></a>Azure Machine Learning

Lorsque vous créez votre propre espace de travail dans Azure Machine Learning Studio, vous devez avoir accès à plus de 400 packages R préinstallés. Vous pouvez également choisir lorsque vous créez une expérience qui utilise R, pour déployer R à l’aide d’une distribution de CRAN R standard, ou Microsoft R Open. Vous pouvez même créer vos propres packages R et les télécharger vers Azure pour exécuter en tant que modules personnalisés.

Pour plus d'informations, consultez ces ressources :

+ [Prolonger votre expérience avec R](https://docs.microsoft.com/azure/machine-learning/machine-learning-extend-your-experiment-with-r)
+ [Auteur modules R personnalisés dans Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/machine-learning-custom-r-modules)

La plupart des algorithmes fournis dans Azure ML sont désormais incluses dans Machine Learning Services, dans le cadre du package MicrosoftML. Pour plus d’informations, consultez [MicrosoftML](https://docs.microsoft.com/r-server/r-reference/microsoftml/microsoftml-package).

Azure Machine Learning est une autre plate-forme pratique pour les données scientifiques et les développeurs qui doivent créer, de l’apprentissage et de déployer des modèles à l’aide des services Web. Vous pouvez publier des solutions pour le [Machine Learning Marketplace](http://datamarket.azure.com/browse/data?category=machine-learning).

### <a name="data-science-virtual-machines"></a>Machines virtuelles pour la science des données

Vous pouvez déployer une version préinstallée et préconfigurée de [!INCLUDE[rsql_platform](../../includes/rsql-platform-md.md)] dans Microsoft Azure, qui vous permet de vous familiariser immédiatement avec l’exploration et la modélisation de données sur le cloud sans installer un système entièrement configuré localement.

Azure Marketplace contient plusieurs machines virtuelles qui prennent en charge la science des données :

+ La **machine virtuelle pour la science des données Microsoft** est configurée avec Microsoft R Server, ainsi que Python (distribution Anaconda), un serveur Jupyter Notebook, Visual Studio Community Edition, Power BI Desktop, le Kit de développement logiciel (SDK) Azure et SQL Server Express Edition.

+ **Microsoft R Server 2016 pour Linux** contient la dernière version de R Server (version 9.0.1). Machines virtuelles distinctes sont disponibles pour CentOS version 7.2 et Ubuntu version 16.04.

+ Le **R Server uniquement SQL Server 2016 Enterprise** machine virtuelle inclut un programme d’installation autonome pour R Server 9.0.1 qui prend en charge le nouveau modèle de licence du cycle de vie logiciel moderne.

> [!TIP]
> La nouvelle [données science des ordinateurs virtuels pour Windows Server 2016](http://aka.ms/dsvm/win2016) fournit des versions GPU des infrastructures de formation approfondie populaires tels que CNTK. Préinstallés, citons les pilotes GPU NVIDIA, CUDA Toolkit 8.0 et la bibliothèque de cuDNN NVIDIA pour les charges de travail GPU. En quelques minutes, vous pouvez avoir un environnement complet pour générer des modèles d’apprentissage approfondie pouvant s’exécuter sur l’UC ou du processeur et d’autre du GPU.

## <a name="next-steps"></a>Étapes suivantes

[Mise en route avec les Services de Machine Learning](getting-started-with-sql-server-r-services.md)

[Prise en main de Machine Learning Server](getting-started-with-microsoft-r-server-standalone.md)

[Installer le moteur de base de données SQL Server](../../database-engine/install-windows/install-sql-server-database-engine.md)
