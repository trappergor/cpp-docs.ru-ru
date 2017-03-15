---
title: "Введение в COM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM"
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Введение в COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Основная модель COM "объектная модель", элементы управления ActiveX и OLE построение.  Модель COM позволяет объекту предоставить свою функциональность другим компонентам и в ведущие приложения.  Оно определяет и как объект предоставляет и в данном фрагменте работает с процессами и по сети.  Модель COM определяет также жизненный цикл объекта.  
  
 Принцип для модели COM эти понятия.  
  
-   [интерфейсы](../atl/interfaces-atl.md) — механизм, с помощью которого объект предоставляет свою функциональность.  
  
-   [IUnknown](../atl/iunknown.md) — базовый интерфейс, в котором все остальные основаны.  Он реализует и интерфейс подсчет ссылок при запросе механизмы, работающих через модель COM.  
  
-   [Подсчет ссылок](../atl/reference-counting.md) — это метод, с помощью которого объект \(или интерфейса\), строго, решают, когда он больше не используется и не является поэтому свободна для удаления.  
  
-   [QueryInterface](../atl/queryinterface.md) — метод, используемый для запроса к объекту для данного интерфейса.  
  
-   [Маршалинг](../atl/marshaling.md) — механизм, который включает объекты, используемые в поток процесса, а границы сети, что позволяет независимости расположения.  
  
-   [агрегат](../atl/aggregation.md) — способ, что объект может использовать другие.  
  
## См. также  
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)   
 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)