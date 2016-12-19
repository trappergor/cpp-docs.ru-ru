---
title: "Точки подключения ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "ATL - библиотека, точки подключения"
  - "точки подключения [C++], сведения о точках подключения"
  - "подключения, точки подключения"
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Точки подключения ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Доступный для подключения объект поддерживает исходящие интерфейсы.  Исходящий интерфейс позволяет объекту обмениваться данными с клиентом.  Для каждого исходящего интерфейса доступный для подключения объект предоставляет точку подключения.  Каждый исходящий интерфейс реализуется клиентов для объекта, который называется приемником.  
  
 ![Точки подключения](../atl/media/vc2zw31.png "vc2ZW31")  
  
 Каждая точка подключения поддерживает интерфейс [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318).  Доступный для подключения объект предоставляет свои точки подключения клиенту через интерфейс [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
## Содержание  
 [Классы точки подключения библиотеки ATL](../atl/atl-connection-point-classes.md)  
 Краткое описание классов ATL, поддерживающих точки подключения.  
  
 [Добавление точек подключения к объектам](../atl/adding-connection-points-to-an-object.md)  
 Описываются действия для добавления точек подключения к объекту.  
  
 [Пример точки подключения ATL](../atl/atl-connection-point-example.md)  
 Пример объявления точки подключения.  
  
## Связанные разделы  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.  
  
## См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)