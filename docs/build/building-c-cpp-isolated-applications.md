---
title: Построение изолированных приложений C/C++
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: 42192ad9388a8e69b70947c20c6fa7ee428a2bb9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220957"
---
# <a name="building-cc-isolated-applications"></a>Построение изолированных приложений C/C++

Изолированное приложение зависит только от side-by-side сборок и привязывается к ним с помощью манифеста. Он не является обязательным для приложения следует полностью изолированы для правильной работы на Windows; Тем не менее Вкладывая средства в создание полностью, может сэкономить время, если для обслуживания приложения в будущем. Дополнительные сведения о преимуществах полностью см. в разделе [изолированных приложений](/windows/desktop/SbsCs/isolated-applications).

При построении собственного C /C++ приложения с помощью Visual Studio по умолчанию в системе проектов Visual Studio создает файл манифеста, описывающий приложения зависимостей от библиотек Visual Studio. Если они все зависимости приложения имеет, то оно становится изолированного приложения, как только оно перестраивается с помощью Visual Studio. Если приложение использует другие библиотеки во время выполнения, то может потребоваться их повторное построение в виде действий, описанных в сборок side-by-side [Создание сборок C/C++-параллельным](building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>См. также

[Основные понятия, связанные с изолированными приложениями и параллельными сборками](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Создание изолированных приложений и параллельных сборок C/C++](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
