---
title: "Interfaces (ATL) | Microsoft Docs"
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
  - "интерфейсы COM"
  - "интерфейсы, COM"
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Interfaces (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Интерфейс способ объект предоставляет свою функциональность с внешним миром.  В модели COM интерфейс таблица указателей \(например C\+\+ vtable\) к функциям указанным объектом.  Таблица представляет интерфейс, и функции, к которому оно указывает методы этого интерфейса.  Объект может предоставлять любое число интерфейсов, так как он выбирает.  
  
 Каждый интерфейс основан на основном интерфейсе модели COM, [IUnknown](../atl/iunknown.md).  Методы позволяют **IUnknown** переход к другим интерфейсов, предоставляемых объектом.  
  
 Кроме того, присваивается каждому интерфейсу уникальный идентификатор интерфейса \(IID\).  Эта уникальность облегчает поддержки управления версиями интерфейса.  Новая версия интерфейса просто новый интерфейс с помощью ИДЕНТИФИКАТОРА.  
  
> [!NOTE]
>  Стандартные IIDs для стандартного модели COM и интерфейсы OLE.  
  
## См. также  
 [Введение в COM](../atl/introduction-to-com.md)   
 [COM Objects and Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms690343)