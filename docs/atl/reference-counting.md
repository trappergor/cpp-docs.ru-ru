---
title: "Reference Counting | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef method [C++]"
  - "AddRef method [C++], reference counting"
  - "reference counting"
  - "reference counts"
  - "ссылки, подсчет"
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Reference Counting
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Модель COM является автоматически не пытается удалить объект из памяти, когда он думает, что объект больше не используется.  Вместо этого, программист объекта должен удалить неиспользуемый объект.  Программист определяет, является ли объект можно удалить на основе счетчике ссылок.  
  
 Модель COM использует методы **IUnknown**, [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуск](http://msdn.microsoft.com/library/windows/desktop/ms682317), чтобы управлять счетчик ссылок интерфейсов объекта.  Общие правила для вызова этих методов:  
  
-   Когда клиент получает указатель интерфейса `AddRef` должен быть вызван в интерфейсе.  
  
-   Когда клиент завершил, используя указатель интерфейса, он должен вызвать **Выпуск**.  
  
 В простой реализации увеличивает каждого вызова `AddRef` и каждое **Выпуск** вызывают уменьшения счетчика переменной в пределах объекта.  После получения количества равным нулю, интерфейс больше не имеют пользователей и свободно удалить из памяти.  
  
 Подсчет ссылок можно также реализовать так, что учитывается каждое ссылку на объект \(не к отдельному интерфейсу\).  В этом случае каждое `AddRef` и **Выпуск** вызывает делегаты в центральной реализации объекта и свободны **Выпуск** весь объект при его достигаемости нулевое значение счетчика ссылок.  
  
> [!NOTE]
>  При `CComObject`\- производный объект создан с помощью оператора **новый**, счетчик ссылок 0.  Поэтому в `AddRef` должен вызываться после успешного создания `CComObject`\- производный объект.  
  
## См. также  
 [Введение в COM](../atl/introduction-to-com.md)   
 [Managing Object Lifetimes through Reference Counting](http://msdn.microsoft.com/library/windows/desktop/ms687260)