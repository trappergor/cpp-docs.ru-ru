---
title: "C++ AMP (C++ Accelerated Massive Parallelism) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 514c45599bce85bf66bf473ac597dab255888ba8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)
C++ AMP (C++ Accelerated Massive Parallelism) ускоряет выполнение кода C++, используя преимущества оборудования параллельными данными, часто присутствует в качестве графического процессора (GPU) на выделенной видеокарте. Модель программирования C++ AMP поддерживает многомерные массивы, индексирование передачи памяти и мозаичное заполнение. Он также включает библиотеки математических функций. Можно использовать расширения языка C++ AMP для управления, как данные перемещаются из ЦП в GPU и обратно.  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание:|  
|-----------|-----------------|  
|[Общие сведения о C++ AMP](../../parallel/amp/cpp-amp-overview.md)|Описание ключевых возможностей C++ AMP и математические библиотеки.|  
|[Использование лямбда-выражений, объектов функций и ограниченных функций](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Описывает способ использования лямбда-выражений, объектов функций и ограниченных функций в вызовах [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) метод.|  
|[Использование плиток](../../parallel/amp/using-tiles.md)|Описывает, как использовать плитки для ускорения выполнения кода C++ AMP.|  
|[Использование объектов accelerator и accelerator_view](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Описывает, как использовать сочетания клавиш для настройки выполнения кода в GPU.|  
|[Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Описывает, как использовать C++ AMP в приложениях универсальной платформы Windows (UWP), которые используют типы среды выполнения Windows.|  
|[Графика (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|Описывает использование графическую библиотеку C++ AMP.|  
|[Пошаговое руководство. Умножение матриц](../../parallel/amp/walkthrough-matrix-multiplication.md)|Демонстрирует умножение матриц с помощью кода C++ AMP и мозаичное заполнение.|  
|[Пошаговое руководство. Отладка приложения C++ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Объясняется, как создать и отладить приложение, использующее параллельной редукции для суммирования большой массив целых чисел.|  
  
## <a name="reference"></a>Ссылка  
 [Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [Ключевое слово tile_static](../../cpp/tile-static-keyword.md)  
  
 [restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)  
  
## <a name="other-resources"></a>Другие ресурсы  
 [Параллельное программирование в блоге машинного кода](http://go.microsoft.com/fwlink/p/?linkid=238472)  
  
 [Образцы проектов C++ AMP для загрузки](http://go.microsoft.com/fwlink/p/?linkid=248508)  
  
 [Анализ кода C++ AMP с помощью визуализатора параллелизма](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)

