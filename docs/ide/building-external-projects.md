---
title: "Построение внешних проектов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- external projects
- Visual C++ projects, external projects
- builds [C++], external projects
- projects [C++], external projects
- Makefile projects, external projects
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16b73349a220f392730dd5526fd5f3d59e59754d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="building-external-projects"></a>Построение внешних проектов
Внешний проект является проектом Visual C++, использующий файл makefile или другие средства, которые находятся за пределами (внешний или внешних по отношению к) в среде разработки Visual C++.  
  
 При наличии внешних проекта (например, проекта makefile), которую требуется построить в среде разработки Visual C++, Создание проекта Makefile и указать команду построения и выходной в мастере приложений Makefile. Дополнительные сведения см. в разделе [Создание проекта Makefile](../ide/creating-a-makefile-project.md).  
  
 Обратите внимание, что Visual C++ больше не поддерживает возможность экспорта файла makefile активного проекта из среды разработки. Используйте [командной строки devenv](/visualstudio/ide/reference/devenv-command-line-switches) для построения проектов Visual Studio из командной строки.  
  
## <a name="see-also"></a>См. также  
 [Сборка проектов C++ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)