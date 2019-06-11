---
title: C++ AMP (C++ Accelerated Massive Parallelism)
ms.date: 11/04/2016
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
ms.openlocfilehash: 3dbd7d646b455ac57833d28b18602b533c8388e6
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450349"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)

C++ AMP (C++ Accelerated Massive Parallelism) ускоряет выполнение кода C++, за счет использования аппаратных средств параллельной обработки данных, таких как графического процессора (GPU) на выделенной видеокарте. Модель программирования C++ AMP включает поддержку многомерных массивов, индексирования, передачи памяти и мозаичного заполнения. Она также включает библиотеку математических функций. Можно использовать расширения языка C++ AMP для управления, как данные перемещаются из ЦП в GPU и обратно.

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|-----------|-----------------|
|[Общие сведения о C++ AMP](../../parallel/amp/cpp-amp-overview.md)|Описание ключевых особенностей C++ AMP и математической библиотеки.|
|[Использование лямбда-выражений, объектов функций и ограниченных функций](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Описывает способ использования лямбда-выражений, объектов функций и ограниченных функций в вызовах [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод.|
|[Использование плиток](../../parallel/amp/using-tiles.md)|Описание использования мозаичных элементов для ускорения кода C++ AMP.|
|[Использование объектов accelerator и accelerator_view](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Описание использования ускорителей для настройки выполнения кода на GPU.|
|[Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|В этой статье описывается использование C++ AMP в приложениях универсальной платформы Windows (UWP), которые используют типы среды выполнения Windows.|
|[Графика (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|Описание использования графической библиотеки C++ AMP.|
|[Пошаговое руководство: умножение матриц](../../parallel/amp/walkthrough-matrix-multiplication.md)|Демонстрирует умножение матриц с помощью кода C++ AMP и мозаичного заполнения.|
|[Пошаговое руководство: отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Объясняется, как создавать и отлаживать приложения, использующего параллельное сокращение для суммирования больших массивов целых чисел.|

## <a name="reference"></a>Ссылка

[Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[Ключевое слово tile_static](../../cpp/tile-static-keyword.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

## <a name="other-resources"></a>Другие ресурсы

[Параллельное программирование в блоге машинного кода](https://go.microsoft.com/fwlink/p/?linkid=238472)<br/>
[Примеры проектов C++ AMP для загрузки](https://go.microsoft.com/fwlink/p/?linkid=248508)<br/>
[Анализ кода C++ AMP с Визуализатором параллелизма](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)