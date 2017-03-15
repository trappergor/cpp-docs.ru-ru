---
title: "Класс IRowsetLocateImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetLocateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "закладки, OLE DB"
  - "IRowsetLocateImpl - класс"
  - "поставщики, закладки"
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс IRowsetLocateImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует интерфейс [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx), OLE DB, который обращается к произвольные строки из набора строк.  
  
## Синтаксис  
  
```  
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >  
>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
   T,   
   RowsetInterface,   
   RowClass,   
   MapClass  
>  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IRowsetLocateImpl`.  
  
 `RowsetInterface`  
 Класс, производный от `IRowsetImpl`.  
  
 `RowClass`  
 Блок памяти для **HROW**.  
  
 `MapClass`  
 Блок памяти для всех дескрипторов строк удержатьых поставщиком.  
  
 `BookmarkKeyType`  
 Тип закладки, например ДЛИННОЕ или строка.  Обычные закладки должны иметь длину не менее 2 байт. Однобайтовая \(длина зарезервировано для OLE DB [стандартные закладки](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK\_FIRST**, **DBBMK\_LAST** и **DBBMK\_INVALID**\).  
  
 `BookmarkType`  
 Механизм сопоставления для поддержки связей закладка\-к\- данных.  
  
 `BookmarkMapClass`  
 Блок памяти для всех дескрипторов строк удержатьых закладкой.  
  
## Члены  
  
### Методы Interface  
  
|||  
|-|-|  
|[Сравнение](../../data/oledb/irowsetlocateimpl-compare.md)|Сравнивает 2 закладки.|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|Получение строк, начиная со строки, заданной смещением от закладки.|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|Получение строк, соответствующих определенным закладкам.|  
|[Хэш](../../data/oledb/irowsetlocateimpl-hash.md)|Возвращает значения хэша для определенных закладок.|  
  
### Элементы данных  
  
|||  
|-|-|  
|[m\_rgBookmarks](../Topic/IRowsetLocateImpl::m_rgBookmarks.md)|Массив закладок.|  
  
## Заметки  
 `IRowsetLocateImpl` реализация интерфейса OLE DB [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx).  `IRowsetLocate` используется для получения произвольные строки из набора строк.  Набор строк, который не реализует этот интерфейс набора строк `sequential`.  При `IRowsetLocate` есть на наборе строк, столбец 0 закладки для строк; чтение в данном столбце получит значение закладки, которую можно использовать для перемещения в одной строке.  
  
 `IRowsetLocateImpl` используется для реализации поддержки закладок в поставщиках.  Закладки заполнители \(индексы в наборе строк\), объект\-получатель позволяет быстро вернуться к строке, позволяя высокоскоростной доступ к данным.  Поставщик указывает, какую закладки могут уникально идентифицировать строку.  С помощью методов `IRowsetLocateImpl`, можно сравнить закладки, получение строк смещением, выборки строк и и возвращает значения хэша для закладок.  
  
 Для поддержки закладок OLE DB в наборе строк используйте набор строк наследовать от этого класса.  
  
 Сведения о реализации поддержки закладок см. в разделе [Поддержка закладок](../../data/oledb/provider-support-for-bookmarks.md) в [Закладки](https://msdn.microsoft.com/en-us/library/ms709728.aspx) в *Visual C\+\+ Programmer's Guide* и *OLE DB Programmer's Reference* в `Platform``SDK`.  
  
## Требования  
 **Заголовок**: atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [Поддержка закладок поставщиками](../../data/oledb/provider-support-for-bookmarks.md)   
 [Bookmarks](https://msdn.microsoft.com/en-us/library/ms709728.aspx)