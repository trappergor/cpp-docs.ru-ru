---
title: C++ AMP (C++ Accelerated Massive Parallelism)
ms.date: 11/04/2016
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
ms.openlocfilehash: c9ef7ab816ec0d17b9dc0b569a6f3a43af83cc68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167697"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)

C++AMP (C++ ускоренный большой параллелизм) ускоряет выполнение C++ кода, используя преимущества аппаратно-ориентированного оборудования, которое обычно представлено в виде графического процессора на дискретной графической карте. Модель C++ программирования amp включает поддержку многомерных массивов, индексирования, перемещения памяти и мозаичного заполнения. Она также содержит математическую библиотеку функций. С помощью C++ расширений языка amp можно управлять перемещением данных из ЦП в GPU и обратно.

## <a name="related-topics"></a>См. также

|Title|Description|
|-----------|-----------------|
|[Общие сведения о C++ AMP](../../parallel/amp/cpp-amp-overview.md)|Описание основных возможностей C++ amp и математической библиотеки.|
|[Использование лямбда-выражений, объектов функций и ограниченных функций](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Описывает использование лямбда-выражений, объектов функций и ограниченных функций в вызовах метода [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) .|
|[Использование плиток](../../parallel/amp/using-tiles.md)|Описание использования плиток для ускорения кода C++ amp.|
|[Использование объектов accelerator и accelerator_view](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Описывает использование ускорителей для настройки выполнения кода на GPU.|
|[Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Описывает, как использовать C++ amp в приложениях универсальная платформа Windows (UWP), использующих типы Среда выполнения Windows.|
|[Графика (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|Описывает использование библиотеки графики C++ amp.|
|[Пошаговое руководство. Умножение матриц](../../parallel/amp/walkthrough-matrix-multiplication.md)|Демонстрирует умножение матрицы C++ с помощью кода amp и мозаичного заполнения.|
|[Пошаговое руководство. Отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Объясняет, как создать и отладить приложение, которое использует Параллельное уменьшение для суммирования большого массива целых чисел.|

## <a name="reference"></a>Справочник

[Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[Ключевое слово tile_static](../../cpp/tile-static-keyword.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

## <a name="other-resources"></a>Другие ресурсы

[Блог о параллельном программировании в машинном коде](https://go.microsoft.com/fwlink/p/?linkid=238472)<br/>
[C++Примеры проектов AMP для загрузки](https://go.microsoft.com/fwlink/p/?linkid=248508)<br/>
[Анализ C++ кода amp с помощью визуализатора параллелизма](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)
