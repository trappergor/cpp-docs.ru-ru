---
title: "Класс IRowsetChangeImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetChangeImpl"
  - "IRowsetChangeImpl"
  - "ATL.IRowsetChangeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetChangeImpl - класс"
  - "поставщики, обновляемые"
  - "поставщики с возможностью обновления, немедленное обновление"
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс IRowsetChangeImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализация интерфейса OLE DB [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) в спецификации OLE DB.  
  
## Синтаксис  
  
```  
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >   
>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IRowsetChangeImpl`.  
  
 `Storage`  
 Запись пользователя.  
  
 `BaseInterface`  
 Базовый класс для интерфейса, например `IRowsetChange`.  
  
 `RowClass`  
 Блок памяти для дескриптора строки.  
  
 `MapClass`  
 Блок памяти для всех дескрипторов строк удержатьых поставщиком.  
  
## Члены  
  
### Методы интерфейса \(\), используемые с IRowsetChange  
  
|||  
|-|-|  
|[DeleteRows](../Topic/IRowsetChangeImpl::DeleteRows.md)|Удаляет строки из набора строк.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|Вставляет строку в набор строк.|  
|[SetData](../Topic/IRowsetChangeImpl::SetData.md)|Задает значения данных в одном или нескольких столбцах.|  
  
### Метод реализации \(обратный вызов\)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|Overidden поставщиком для сохранения данных в его хранилище.|  
  
## Заметки  
 Этот интерфейс должен для интерпретации операции записи в хранилище данных. «Немедленный» означает, что если пользователь \(человеком, использующим объект\-получателя\), все изменения, эти изменения немедленно передаются в хранилище данных \(и не может быть отменено\).  
  
 `IRowsetChangeImpl` реализует интерфейс OLE DB `IRowsetChange`, который позволяет обновлять значений столбцов в существующих строках, удаление строки и вставки новых строк.  
  
 Реализация шаблонов OLE DB поддерживает все базовые методы \(`SetData`, `InsertRow` и `DeleteRows`\).  
  
> [!IMPORTANT]
>  Настоятельно рекомендуется чтении следующую документацию ПЕРЕД попыткой реализации поставщика:  
  
-   [Создание обновляемого поставщика](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Глава 6 *OLE DB Programmer's Reference*  
  
-   Также см. раздел как класс `RUpdateRowset` используется в примере UpdatePV  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)