---
title: "класс CSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSession"
  - "ATL::CSession"
  - "ATL.CSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession - класс"
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# класс CSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет один сеанс доступа к базе данных.  
  
## Синтаксис  
  
```  
class CSession  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[Прервать](../Topic/CSession::Abort.md)|Отменяет \(\) используется для завершения транзакции.|  
|[Закрыть](../../data/oledb/csession-close.md)|Закрывает сеанс.|  
|[Фиксация](../../data/oledb/csession-commit.md)|Завершает транзакцию.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Возвращает сведения о транзакции.|  
|[Откройте .](../../data/oledb/csession-open.md)|Открывает новый сеанс для объекта источника данных.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Начинает новую транзакцию для данного сеанса.|  
  
## Заметки  
 Один или несколько сеансов можно связать с каждым подключения поставщика \(источником данных\), которое представлено объектом [CDataSource](../Topic/CDataSource%20Class.md).  Для создания нового `CSession` для `CDataSource`, вызовите метод [CSession::Open](../../data/oledb/csession-open.md).  Чтобы начать транзакцию базы данных, `CSession` предоставляет метод `StartTransaction`.  Если транзакция запущена, можно также выполнять к ним с помощью метода **Зафиксировать**, или отменить их с помощью метода **Прервать**.  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [CatDB](../../top/visual-cpp-samples.md)   
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)