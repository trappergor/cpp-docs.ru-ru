---
title: Начало работы с аналитикой сборки C++
description: Общий обзор C++ Build Insights.
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c4ebbb280a5cccaa35b5efc7f90e9b570600c47b
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923630"
---
# <a name="get-started-with-c-build-insights"></a>Начало работы с аналитикой сборки C++

::: moniker range="<=msvc-150"

Средства C++ Build Insights доступны в Visual Studio 2019. Чтобы отобразилась документация для этой версии, установите в этой статье селектор **Версия** Visual Studio в положение "Visual Studio 2019". Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range="msvc-160"

C++ Build Insights — это набор инструментов, предоставляющих подробные сведения о цепочке инструментов Microsoft Visual C++ (MSVC). Инструменты собирают данные о сборках C++ и представляют их в формате, который может помочь вам получить ответы на распространенные вопросы, например:

- Параллелизованы ли сборки надлежащим образом?
- Что нужно включить в предкомпилированный заголовок (PCH)?
- Есть ли определенные проблемы, которые нужно устранить для ускорения сборки?

Основные компоненты этой технологии:

- *vcperf.exe*  — служебная программа командной строки, которую можно использовать для получения трассировок сборок;
- расширение Windows Performance Analyzer (WPA), позволяющее просматривать трассировки сборок в WPA;
- пакет SDK для C++ Build Insights для создания собственных инструментов, использующих данные C++ Build Insights.

## <a name="documentation-sections"></a>Разделы документации

[Руководство. Средство vcperf и Windows Performance Analyzer](tutorials/vcperf-and-wpa.md)\
Узнайте, как собирать данные трассировки сборок для проектов C++ и как просматривать их в WPA.

[Учебник. Основные сведения о производительности Windows](tutorials/wpa-basics.md)\
Ознакомьтесь с полезными советами по использованию WPA для анализа трассировок сборок.

[Пакет SDK для C++ Build Insights](reference/sdk/overview.md)\
Обзор пакета SDK для C++ Build Insights.

## <a name="articles"></a>Статьи

Дополнительные сведения о C++ Build Insights см. в следующих статьях в официальном блоге разработчиков C++:

[Введение в C++ Build Insights](https://devblogs.microsoft.com/cppblog/introducing-c-build-insights/)

[Программный анализ сборок с помощью пакета SDK для C++ Build Insights](https://devblogs.microsoft.com/cppblog/analyze-your-builds-programmatically-with-the-c-build-insights-sdk/)

[Поиск узких мест в сборках с помощью C++ Build Insights](https://devblogs.microsoft.com/cppblog/finding-build-bottlenecks-with-cpp-build-insights/)

[Ускорение сборки благодаря рекомендациям относительно PCH от C++ Build Insights](https://devblogs.microsoft.com/cppblog/faster-builds-with-pch-suggestions-from-c-build-insights/)

::: moniker-end
