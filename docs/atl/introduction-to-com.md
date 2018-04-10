---
title: Общие сведения о COM | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a8953949e722265afabc22410174b84c017276c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-com"></a>Знакомство с COM
COM является фундаментальные «объект модели» на элементы управления ActiveX и OLE, которые построены. COM позволяет объекту предоставлять его функциональность другим компонентам и приложениям хоста. Он определяет, как объект предоставляет доступ к самой и как работает этот раскрытия всех процессов и в сети. Модель COM также определяет жизненный цикл объекта.  
  
 Основа для COM этих концепций:  
  
-   [Интерфейсы](../atl/interfaces-atl.md) — это механизм, через который объект предоставляет свои функции.  
  
-   [IUnknown](../atl/iunknown.md) — базовый интерфейс, на котором основаны все остальные. Он реализует подсчет ссылок и интерфейс запросов механизмы обработки с помощью модели COM.  
  
-   [Подсчет ссылок](../atl/reference-counting.md) — способ, с помощью которого объект (или, строго говоря, интерфейс) определяет, когда больше не используется и поэтому он может удалить себя.  
  
-   [QueryInterface](../atl/queryinterface.md) — метод, используемый для запроса объекта для заданного интерфейса.  
  
-   [Маршалинг](../atl/marshaling.md) — механизм, позволяющий объектов для использования в нескольких потоков процесса и границы сети, что обеспечивает независимость от местонахождения.  
  
-   [Агрегат](../atl/aggregation.md) — способом, в которой один объект можно использовать для другого.  
  
## <a name="see-also"></a>См. также  
 [Введение в COM и библиотеки ATL](../atl/introduction-to-com-and-atl.md)   
 [Модель COM](http://msdn.microsoft.com/library/windows/desktop/ms694363)

