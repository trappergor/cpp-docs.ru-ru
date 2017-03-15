---
title: "Класс CRowsetImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl"
  - "ATL.CRowsetImpl"
  - "ATL::CRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRowsetImpl - класс"
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс CRowsetImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет стандартную реализацию набора строк OLE DB, без необходимости множественного наследования множество интерфейсов реализации.  
  
## Синтаксис  
  
```  
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl < T, IRowset >   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### Параметры  
 `T`  
 Класс, производный от пользователя `CRowsetImpl`.  
  
 `Storage`  
 Класс записей пользователя.  
  
 `CreatorClass`  
 Класс, который содержит свойства для набора строк; обычно команды.  
  
 `ArrayType`  
 Класс, который будет выступать в качестве хранилища для данных набора строк.  Этот параметр устанавливается значение по умолчанию `CAtlArray`, но может быть любой класс, который поддерживает необходимую функциональность.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|Извлекает строки из **DBID** и копирует ее в `bstr` проведенному недопустимо.|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|Проверяет и сохраняет **DBID** в слове 2 строк \([m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\).|  
  
### Методы Overridable  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|Извлекает сведения о столбцах для определенного запроса клиента.|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|Проверяет, является ли один или оба параметры содержат строковые значения, и если да, копирования строковые значения элементам данных [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|Проверяет, является ли любой или и **DBID**, содержащий строковые значения, и если да, скопируйте их в элементов данных [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
  
### Элементы данных  
  
|||  
|-|-|  
|[m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|По умолчанию `CAtlArray`, templatizes в аргументе шаблона записи пользователя в `CRowsetImpl`.  Другой класс типа массива может использоваться путем изменения аргумент шаблона `ArrayType` в `CRowsetImpl`.|  
|[m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|Содержит команду набора строк начальную.|  
|[m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|Содержит индекс начального набора строк.|  
  
## Заметки  
 `CRowsetImpl` предоставляет переопределения в форме статических upcasts.  Управление методов изображение, в котором заданный набор строк проверяет текст команды.  Можно создать собственный класс `CRowsetImpl` в стиле, выполнив на несколько наследуемые реализации интерфейсов.  Единственный метод, для которого необходимо предоставить реализацию **Выполнить**.  В зависимости от типа набора строк, который необходимо создать, методы создания требуется различные сигнатуры для **Выполнить**.  Например, при использовании `CRowsetImpl`\- производный класс, который будет реализовать, набор строк схемы, метод **Выполнить** будет иметь следующую сигнатуру:  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 При создании `CRowsetImpl`\- производный класс, который будет реализовать, набор строк команды или сеанса, метод **Выполнить** будет иметь следующую сигнатуру:  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 Реализовывать любое `CRowsetImpl`\- производные методы **Выполнить** необходимо заполнение буферы внутренних данных \([m\_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)\).  
  
## Требования  
 **Header:** atldb.h