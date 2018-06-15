---
title: Сборка внешних проектов | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- external projects
- Visual C++ projects, external projects
- builds [C++], external projects
- projects [C++], external projects
- Makefile projects, external projects
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97b6aa1e5939afe55644df6529bf75ba043f20bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330350"
---
# <a name="building-external-projects"></a>Построение внешних проектов
Внешний проект — это проект Visual C++, который использует файл makefile или другие средства, расположенные вне (за пределами) среды разработки Visual C++.  
  
 При наличии внешнего проекта (например, проекта, использующего файл makefile), который требуется собрать в среде разработки Visual C++, создайте проект с файлом makefile и укажите команду сборки и выходные данные своего проекта в мастере приложений makefile. Дополнительные сведения см. в разделе [Создание проекта makefile](../ide/creating-a-makefile-project.md).  
  
 Обратите внимание, что Visual C++ больше не поддерживает экспорт файла makefile для активного проекта из среды разработки. Используйте [параметры командной строки devenv](/visualstudio/ide/reference/devenv-command-line-switches) для сборки проектов Visual Studio из командной строки.  
  
## <a name="see-also"></a>См. также  
 [Сборка проектов C++ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)