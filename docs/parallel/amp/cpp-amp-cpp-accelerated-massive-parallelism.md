---
title: "C++ AMP (C++ Accelerated Massive Parallelism) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ Accelerated Massive Parallelism, начало работы"
  - "C++ AMP (см. C++ Accelerated Massive Parallelism)"
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
caps.latest.revision: 22
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ AMP (C++ Accelerated Massive Parallelism)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ Accelerated Massive Parallelism \(C\+\+ AMP\) ускоряет выполнение кода C\+\+, получая преимущества от использования аппаратных средств параллельной обработки данных, таких как графический процессор \(GPU\) на дискретной видеокарте.  Модель программирования C\+\+ AMP включает поддержку многомерных массивов, индексирования, передачи памяти и мозаичного заполнения.  Она также включает библиотеку математических функций.  Можно использовать расширения языка C\+\+ AMP для мониторинга того, как данные перемещаются из ЦП в GPU и обратно.  
  
## Связанные разделы  
  
|Название|Описание|  
|--------------|--------------|  
|[Общие сведения о C\+\+ AMP](../../parallel/amp/cpp-amp-overview.md)|Описание основных функций C\+\+ AMP и математической библиотеки.|  
|[Использование лямбда\-выражений, объектов функций и ограниченных функций](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|Описание использования лямбда\-выражений, функциональных объектов и функций с ограничениями при вызовах метода [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).|  
|[Использование плиток](../../parallel/amp/using-tiles.md)|Описание использования мозаичных элементов для ускорения кода C\+\+ AMP.|  
|[Использование объектов accelerator и accelerator\_view](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|Описание использования ускорителей для настройки выполнения кода на GPU.|  
|[Использование C\+\+ AMP в приложениях для Магазина Windows](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Описание использования C\+\+ AMP в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], которые используют типы среды выполнения Windows.|  
|[Графика \(C\+\+ AMP\)](../../parallel/amp/graphics-cpp-amp.md)|Описание использования графической библиотеки C\+\+ AMP.|  
|[Пошаговое руководство. Умножение матриц](../../parallel/amp/walkthrough-matrix-multiplication.md)|Демонстрирует умножение матриц с помощью кода C\+\+ AMP и мозаичного заполнения.|  
|[Пошаговое руководство. Отладка приложения C\+\+ AMP](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|Описываются создание и отладка приложения, использующего параллельное сокращение для суммирования больших массивов целых чисел.|  
  
## Справочные сведения  
 [Справочник \(C\+\+ AMP\)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [Ключевое слово tile\_static](../Topic/tile_static%20Keyword.md)  
  
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)  
  
## Другие ресурсы  
 [Параллельное программирование в блоге "Машинный код"](http://go.microsoft.com/fwlink/p/?LinkId=238472)  
  
 [Примеры проектов C\+\+ AMP для загрузки](http://go.microsoft.com/fwlink/p/?LinkId=248508)  
  
 [Анализ кода C\+\+ AMP с визуализатором параллелизма](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)