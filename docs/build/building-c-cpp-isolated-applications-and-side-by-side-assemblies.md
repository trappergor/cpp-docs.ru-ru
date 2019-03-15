---
title: Построение изолированных приложений и параллельных сборок C/C++
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
ms.openlocfilehash: e3c39595008d92b390b03a56bdcf5fc8990b2103
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807563"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>Построение изолированных приложений и параллельных сборок C/C++

Visual C++ поддерживает модель развертывания клиентских приложений Windows, основанную на идее [изолированных приложений](/windows/desktop/SbsCs/isolated-applications) и [параллельных сборок](/windows/desktop/SbsCs/about-side-by-side-assemblies-). По умолчанию Visual C++ выполняет построение всех машинных приложений C/C++ в качестве изолированных приложений, использующих [манифесты](/windows/desktop/sbscs/manifests) для описания зависимостей от библиотек Visual C++.

Построение программ C/C++ в качестве изолированных приложений предоставляет множество преимуществ. Например, на изолированное приложение не влияет установка или удаление библиотек Visual C++ другими приложениями C/C++. Библиотеки Visual C++, используемые изолированными приложениями, по-прежнему могут распространяться в локальной папке приложения либо путем установки в собственный кэш сборок (WinSxS). Тем не менее обслуживание библиотек Visual C++ для уже развернутых приложений можно упростить, воспользовавшись [файлом конфигурации издателя](/windows/desktop/SbsCs/publisher-configuration). С помощью модели развертывания изолированных приложений проще гарантировать, что приложения C/C++, выполняющиеся на конкретном компьютере, будут использовать самые свежие версии библиотек Visual C++, по-прежнему предоставляя системным администраторам и авторам приложений возможность управления явной привязкой версий приложений к зависимым библиотекам DLL.

В этом разделе рассматриваются способы построения изолированного приложения C/C++ и обеспечения его привязки к библиотекам Visual C++ с помощью манифеста. Сведения в этом разделе в первую очередь актуальны для машинных (или неуправляемых) приложений Visual C++. Подробнее о развертывании машинных приложений, построенных с помощью Visual C++, см. в статье [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).

## <a name="in-this-section"></a>В этом разделе

[Основные понятия, связанные с изолированными приложениями и параллельными сборками](concepts-of-isolated-applications-and-side-by-side-assemblies.md)

[Создание изолированных приложений на C/C++](building-c-cpp-isolated-applications.md)

[Создание параллельных сборок на C/C++](building-c-cpp-side-by-side-assemblies.md)

[Практическое руководство. Сборка не требующих регистрации компонентов COM](how-to-build-registration-free-com-components.md)

[Практическое руководство. Сборка изолированных приложений, использующих компоненты СОМ](how-to-build-isolated-applications-to-consume-com-components.md)

[Основные сведения о создании манифестов для программ на C/C++](understanding-manifest-generation-for-c-cpp-programs.md)

[Устранение неполадок в изолированных приложениях и параллельных сборках на C/C++](troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="related-sections"></a>Связанные разделы

[Изолированные приложения и параллельные сборки](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)

[Развертывание классических приложений](../ide/deploying-native-desktop-applications-visual-cpp.md)