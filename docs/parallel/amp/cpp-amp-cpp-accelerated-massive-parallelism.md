---
title: C++ AMP (C++ Accelerated Massive Parallelism)
ms.date: 11/04/2016
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
ms.openlocfilehash: 516b69a0371ceb9365e79d5465879711289076c0
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404864"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)

C++ AMP (C++ Accelerated Massive Parallelism) ускоряет выполнение кода C++, используя преимущества аппаратно-ориентированного оборудования, которое обычно представлено в виде графического процессора на дискретной графической карте. Модель программирования C++ AMP включает поддержку многомерных массивов, индексирования, перемещения памяти и мозаичного заполнения. Она также содержит математическую библиотеку функций. Для управления перемещением данных из ЦП в GPU и обратно можно использовать расширения языка C++ AMP.

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Обзор C++ AMP](../../parallel/amp/cpp-amp-overview.md)|Описание основных возможностей C++ AMP и математической библиотеки.|
|[Использование лямбда-выражений, объектов функций и ограниченных функций](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Описывает использование лямбда-выражений, объектов функций и ограниченных функций в вызовах метода [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) .|
|[Использование плиток](../../parallel/amp/using-tiles.md)|Описание использования плиток для ускорения кода C++ AMP.|
|[Использование ускорителей и объектов accelerator_view](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Описывает использование ускорителей для настройки выполнения кода на GPU.|
|[Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Описывает, как использовать C++ AMP в приложениях универсальная платформа Windows (UWP), использующих типы среда выполнения Windows.|
|[Графика (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|Описывает использование библиотеки C++ AMP Graphics.|
|[Пошаговое руководство. умножение матрицы](../../parallel/amp/walkthrough-matrix-multiplication.md)|Демонстрирует умножение матрицы с помощью C++ AMPного кода и мозаичного заполнения.|
|[Пошаговое руководство: отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Объясняет, как создать и отладить приложение, которое использует Параллельное уменьшение для суммирования большого массива целых чисел.|

## <a name="reference"></a>Справочник

[Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[Ключевое слово tile_static](../../cpp/tile-static-keyword.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

## <a name="other-resources"></a>Другие ресурсы

[Блог о параллельном программировании в машинном коде](https://go.microsoft.com/fwlink/p/?linkid=238472)<br/>
[C++ AMP образцы проектов для загрузки](https://go.microsoft.com/fwlink/p/?linkid=248508)<br/>
[Анализ кода C++ AMP с помощью визуализатора параллелизма](/archive/blogs/nativeconcurrency/analyzing-c-amp-code-with-the-concurrency-visualizer)
