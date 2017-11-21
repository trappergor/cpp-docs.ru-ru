---
title: "Точки подключения ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e0ef927ad6e2a0e9b0c71e211fa525ba7fc8ea0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="atl-connection-points"></a>Точки подключения ATL
Доступный для подключения объект поддерживает исходящие интерфейсы. Исходящий интерфейс позволяет объекту обмениваться данными с клиентом. Для каждого исходящего интерфейса доступный для подключения объект предоставляет точку подключения. Каждый исходящий интерфейс реализуется клиентов для объекта, который называется приемником.  
  
 ![Точки подключения](../atl/media/vc2zw31.gif "vc2zw31")  
  
 Каждая точка подключения поддерживает [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) интерфейса. Доступный для соединения объект предоставляет свои точки подключения клиенту через [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857) интерфейса.  
  
## <a name="in-this-section"></a>Содержание  
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

