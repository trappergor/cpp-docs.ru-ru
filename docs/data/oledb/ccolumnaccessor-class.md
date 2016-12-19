---
title: "Класс CColumnAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CColumnAccessor"
  - "ATL::CColumnAccessor"
  - "ATL.CColumnAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnAccessor - класс"
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CColumnAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generates впрыснул код объект\-получателя.  
  
## Синтаксис  
  
```  
class CColumnAccessor : public CAccessorBase  
```  
  
## Заметки  
 В просмотре введенного кода, каждый столбец привязан как отдельные доступ.  Следует иметь в виду, что этот класс используется в просмотре введенного кода \(например, можно получить его отладки\), но обычно никогда не должны использовать его или ее методы напрямую.  
  
 `CColumnAccessor` реализует следующие методы заглушки, каждый из которых совпадают в функции к другим методам класса доступа.  
  
-   `CColumnAccessor` конструктор; создает и инициализирует объект `CColumnAccessor`.  
  
-   `CreateAccessor` выделяет память для структур привязку столбцов и инициализирует члены данных столбца.  
  
-   **BindColumns** связывает столбцы с целью.  
  
-   **SetParameterBuffer** выделяет буферы для параметров.  
  
-   `AddParameter` добавляет запись параметра к структурам записи параметра.  
  
-   **HasOutputColumns** определяет, есть ли доступ выходные столбцы  
  
-   **HasParameters** определяет, есть ли доступ параметры.  
  
-   `BindParameters` привязывает параметры, созданные со столбцами.  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)