---
title: "CRowsetImpl::GetColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetColumnInfo"
  - "CRowsetImpl.GetColumnInfo"
  - "CRowsetImpl::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo - метод"
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CRowsetImpl::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает сведения о столбцах для определенного запроса клиента.  
  
## Синтаксис  
  
```  
  
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(  
   T* pv,  
   ULONG* pcCols   
);  
```  
  
#### Параметры  
 `pv`  
 \[in\] указатель на производный класс `CRowsetImpl` пользователя.  
  
 `pcCols`  
 \[in\] указатель a \(вывода\) с количеством столбцов является.  
  
## Возвращаемое значение  
 Указатель на структуру **ATLCOLUMNINFO** статической.  
  
## Заметки  
 Этот метод дополнительное переопределить.  
  
 Этот метод вызывается несколько классов базовую реализацию для получения информации о столбцах для определенного запроса клиента.  Обычно этот метод будет вызван `IColumnsInfoImpl`.  Если переопределите этот метод, необходимо установить версию метода в `CRowsetImpl`\- производного класса.  Поскольку метод может поместить в non\-templatized классе, необходимо изменить `pv` соответствующему `CRowsetImpl`\- производного класса.  
  
 В следующем примере демонстрируется потребление **GetColumnInfo's**.  В этом примере **CMyRowset**`CRowsetImpl`\- производного класса.  Для переопределения `GetColumnInfo` для всех экземпляров этого класса, добавьте следующий метод в определении класса **CMyRowset**:  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/CPP/crowsetimpl-getcolumninfo_1.h)]  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)