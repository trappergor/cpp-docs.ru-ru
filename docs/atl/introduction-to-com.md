---
title: Общие сведения о COM | Документы Microsoft
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 938d0c45cae5ec9a2988f77f539af1a3d5513b83
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

