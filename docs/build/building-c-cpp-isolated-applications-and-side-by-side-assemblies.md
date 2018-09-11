---
title: Построение C/C++ изолированных приложений и сборок Side-by-side | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8d806af709d6d6e2a5754bc80a34a473900177f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212916"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>Построение изолированных приложений и параллельных сборок C/C++
Visual C++ поддерживает модель развертывания клиентских приложений Windows, основанную на идее [изолированных приложений](/windows/desktop/SbsCs/isolated-applications) и [сборок side-by-side](/windows/desktop/SbsCs/about-side-by-side-assemblies-). По умолчанию Visual C++, выполняет построение всех машинных приложений C/C++ в изолированных приложений, использующих [манифесты](https://msdn.microsoft.com/library/aa375365) для описания зависимостей от библиотек Visual C++.  
  
 Построение программ C/C++ в качестве изолированных приложений предоставляет множество преимуществ. Например, на изолированное приложение не влияет установка или удаление библиотек Visual C++ другими приложениями C/C++. Библиотеки Visual C++, используемые изолированными приложениями могут по-прежнему распространяться в локальной папке приложения либо путем установки в собственный кэш сборок (WinSxS); Тем не менее обслуживание библиотек Visual C++ для уже развернутых приложений можно упростить с помощью [файлом конфигурации издателя](/windows/desktop/SbsCs/publisher-configuration). С помощью модели развертывания изолированных приложений проще гарантировать, что приложения C/C++, выполняющиеся на конкретном компьютере, будут использовать самые свежие версии библиотек Visual C++, по-прежнему предоставляя системным администраторам и авторам приложений возможность управления явной привязкой версий приложений к зависимым библиотекам DLL.  
  
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
 [Изолированные приложения и сборки Side-by-side](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)  
  
 [Развертывание классических приложений](../ide/deploying-native-desktop-applications-visual-cpp.md)