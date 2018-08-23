---
title: C++ AMP (C++ Accelerated Massive Parallelism) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a990acd8f27be476ce35d682a19912dcc85bbeed
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42541848"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)
C++ AMP (C++ Accelerated Massive Parallelism) ускоряет выполнение кода C++, за счет использования аппаратных средств параллельной обработки данных, таких как графического процессора (GPU) на выделенной видеокарте. Модель программирования C++ AMP включает поддержку многомерных массивов, индексирования, передачи памяти и мозаичного заполнения. Она также включает библиотеку математических функций. Можно использовать расширения языка C++ AMP для управления, как данные перемещаются из ЦП в GPU и обратно.  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание:|  
|-----------|-----------------|  
|[Общие сведения о C++ AMP](../../parallel/amp/cpp-amp-overview.md)|Описание ключевых особенностей C++ AMP и математической библиотеки.|  
|[Использование лямбда-выражений, объектов функций и ограниченных функций](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Описывает способ использования лямбда-выражений, объектов функций и ограниченных функций в вызовах [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод.|  
|[Использование плиток](../../parallel/amp/using-tiles.md)|Описание использования мозаичных элементов для ускорения кода C++ AMP.|  
|[Использование объектов accelerator и accelerator_view](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Описание использования ускорителей для настройки выполнения кода на GPU.|  
|[Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|В этой статье описывается использование C++ AMP в приложениях универсальной платформы Windows (UWP), которые используют типы среды выполнения Windows.|  
|[Графика (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|Описание использования графической библиотеки C++ AMP.|  
|[Пошаговое руководство. Умножение матриц](../../parallel/amp/walkthrough-matrix-multiplication.md)|Демонстрирует умножение матриц с помощью кода C++ AMP и мозаичного заполнения.|  
|[Пошаговое руководство. Отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Объясняется, как создавать и отлаживать приложения, использующего параллельное сокращение для суммирования больших массивов целых чисел.|  
  
## <a name="reference"></a>Ссылка  

[Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)    
[Ключевое слово tile_static](../../cpp/tile-static-keyword.md)    
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)  
  
## <a name="other-resources"></a>Другие ресурсы  
 
[Параллельное программирование в блоге машинного кода](http://go.microsoft.com/fwlink/p/?linkid=238472)  
[Примеры проектов C++ AMP для загрузки](http://go.microsoft.com/fwlink/p/?linkid=248508)  
[Анализ кода C++ AMP с Визуализатором параллелизма](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)