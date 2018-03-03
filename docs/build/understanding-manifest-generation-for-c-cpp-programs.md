---
title: "Основные сведения о создании манифестов для программ C/C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 848b4b449fa2c9c8930a616b70a5b61cb28d8fbf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>Основные сведения о создании манифестов для программ C/C++
Объект [манифеста](http://msdn.microsoft.com/library/aa375365) внедренного XML-документ, который может быть внешним файлом XML или ресурс в приложение или сборку. Манифест [изолированное приложение](http://msdn.microsoft.com/library/aa375190) используется для управления именами и версиями совместно с параллельных сборок, к которым должно быть связано приложение во время выполнения. Манифест сборки side-by-side задает ее зависимости от имен, версий, ресурсов и других сборок.  
  
 Существует два способа создания манифеста для изолированного приложения или side-by-side сборки. Во-первых автор сборки можно вручную создать файл манифеста, в соответствии с правилами и требования к именованию. Кроме того Если программа зависит только от сборки Visual C++, такие как CRT, MFC, ATL или других лиц, затем манифест может генерироваться автоматически компоновщиком.  
  
 Заголовки библиотек Visual C++, содержат сведения о сборке, и когда библиотеки включаются в код приложения, эти сведения используются компоновщиком манифеста для конечного двоичного файла. Компоновщик не встраивает файл манифеста в двоичный файл и может формировать только манифест в виде внешнего файла. Внешний файл манифеста может работать не для всех сценариев. Например рекомендуется, закрытых сборок с внедренными манифесты. В сборках командной строки, например те, которые используют для создания кода nmake манифест может быть внедрен с помощью инструмента манифеста; Дополнительные сведения см. [создание манифеста в командной строке](../build/manifest-generation-at-the-command-line.md). При выполнении сборки в [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], манифест может быть внедрен путем задания свойства для инструмента манифеста в **свойства проекта** диалогового окна см. в разделе [создание манифеста в Visual Studio](../build/manifest-generation-in-visual-studio.md).  
  
## <a name="see-also"></a>См. также  
 [Концепции изолированных приложений и сборок Side-by-side](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Создание изолированных приложений и параллельных сборок C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)