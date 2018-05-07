---
title: Точки подключения ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 179f4329d55261d71d3d122e6a2601ce7e805c0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-connection-points"></a>Точки подключения ATL
Доступный для подключения объект поддерживает исходящие интерфейсы. Исходящий интерфейс позволяет объекту обмениваться данными с клиентом. Для каждого исходящего интерфейса доступный для подключения объект предоставляет точку подключения. Каждый исходящий интерфейс реализуется клиентов для объекта, который называется приемником.  
  
 ![Точки подключения](../atl/media/vc2zw31.gif "vc2zw31")  
  
 Каждая точка подключения поддерживает [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) интерфейса. Доступный для соединения объект предоставляет свои точки подключения клиенту через [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857) интерфейса.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Классы точки подключения библиотеки ATL](../atl/atl-connection-point-classes.md)  
 Краткое описание классов ATL, поддерживающих точки подключения.  
  
 [Добавление точек подключения к объектам](../atl/adding-connection-points-to-an-object.md)  
 Описываются действия для добавления точек подключения к объекту.  
  
 [Пример точки подключения ATL](../atl/atl-connection-point-example.md)  
 Пример объявления точки подключения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

