---
title: "Построение C/C++ изолированных приложений и сборок Side-by-side | Документы Microsoft"
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
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5dec3b0db6d77cc11d0e2ccdc97fe54ab8e0624
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>Построение изолированных приложений и параллельных сборок C/C++
Visual C++ поддерживает модель развертывания клиентских приложений Windows, основанную на идее [изолированных приложений](http://msdn.microsoft.com/library/aa375190) и [параллельных сборок](http://msdn.microsoft.com/library/ff951640). По умолчанию Visual C++ выполняет построение всех машинных приложений C/C++ в качестве изолированных приложений, использующих [манифесты](http://msdn.microsoft.com/library/aa375365) для описания зависимостей от библиотек Visual C++.  
  
 Построение программ C/C++ в качестве изолированных приложений предоставляет множество преимуществ. Например, на изолированное приложение не влияет установка или удаление библиотек Visual C++ другими приложениями C/C++. Библиотеки Visual C++, используемые изолированными приложениями, по-прежнему могут распространяться в локальной папке приложения либо путем установки в собственный кэш сборок (WinSxS). Тем не менее обслуживание библиотек Visual C++ для уже развернутых приложений можно упростить, воспользовавшись [файлом конфигурации издателя](http://msdn.microsoft.com/library/aa375680). С помощью модели развертывания изолированных приложений проще гарантировать, что приложения C/C++, выполняющиеся на конкретном компьютере, будут использовать самые свежие версии библиотек Visual C++, по-прежнему предоставляя системным администраторам и авторам приложений возможность управления явной привязкой версий приложений к зависимым библиотекам DLL.  
  
 В этом разделе рассматриваются способы построения изолированного приложения C/C++ и обеспечения его привязки к библиотекам Visual C++ с помощью манифеста. Сведения в этом разделе в первую очередь актуальны для машинных (или неуправляемых) приложений Visual C++. Подробнее о развертывании машинных приложений, построенных с помощью Visual C++, см. в статье [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Основные понятия, связанные с изолированными приложениями и параллельными сборками](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)  
  
 [Создание изолированных приложений на C/C++](../build/building-c-cpp-isolated-applications.md)  
  
 [Создание параллельных сборок на C/C++](../build/building-c-cpp-side-by-side-assemblies.md)  
  
 [Практическое руководство. Сборка не требующих регистрации компонентов COM](../build/how-to-build-registration-free-com-components.md)  
  
 [Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
 [Основные сведения о создании манифестов для программ на C/C++](../build/understanding-manifest-generation-for-c-cpp-programs.md)  
  
 [Устранение неполадок в изолированных приложениях и параллельных сборках на C/C++](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
## <a name="related-sections"></a>Связанные разделы  
 [Изолированные приложения и параллельные сборки](http://msdn.microsoft.com/library/dd408052)  
  
 [Развертывание приложений для настольных систем](../ide/deploying-native-desktop-applications-visual-cpp.md)