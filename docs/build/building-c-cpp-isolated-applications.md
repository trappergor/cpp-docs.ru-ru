---
title: Создание изолированных приложений C/C++ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78d14f812700afa4ea0ad66b527a0e3888862f4d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716914"
---
# <a name="building-cc-isolated-applications"></a>Построение изолированных приложений C/C++

Изолированное приложение зависит только от side-by-side сборок и привязывается к ним с помощью манифеста. Он не является обязательным для приложения следует полностью изолированы для правильной работы на Windows; Тем не менее Вкладывая средства в создание полностью, может сэкономить время, если для обслуживания приложения в будущем. Дополнительные сведения о преимуществах полностью см. в разделе [изолированных приложений](/windows/desktop/SbsCs/isolated-applications).

При создании собственного приложения C/C++ с помощью Visual C++, Visual Studio по умолчанию система проекта создает файл манифеста, который описывает зависимости приложения от библиотек Visual C++. Если они все зависимости приложения имеет, то оно становится изолированного приложения, как только оно перестраивается с помощью Visual Studio. Если приложение использует другие библиотеки во время выполнения, то может потребоваться их повторное построение в виде действий, описанных в сборок side-by-side [Создание сборок C/C++-параллельным](../build/building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>См. также

[Основные понятия, связанные с изолированными приложениями и параллельными сборками](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Создание изолированных приложений и параллельных сборок C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)