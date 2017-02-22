---
title: "Класс CCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CCommand"
  - "CCommand"
  - "ATL.CCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCommand - класс"
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс CCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет методы для настройки и выполнения.  
  
## Синтаксис  
  
```  
template <  
   class TAccessor = CNoAccessor,  
   template < typename T > class TRowset = CRowset,  
   class TMultiple = CNoMultipleResults   
>  
class CCommand :   
   public CAccessorRowset <  
      TAccessor,   
      TRowset   
   >,  
   public CCommandBase,  
   public TMultiple  
```  
  
#### Параметры  
 `TAccessor`  
 Тип класса доступа \(например `CDynamicParameterAccessor`, `CDynamicStringAccessor` или `CEnumeratorAccessor`\), необходимо использовать команду.  По умолчанию `CNoAccessor`, которое указывает, что параметры или класса не поддерживают выходные столбцы.  
  
 `TRowset`  
 Тип класса набора строк \(например, `CArrayRowset` или `CNoRowset`\), необходимо использовать команду.  Значение по умолчанию — `CRowset`.  
  
 `TMultiple`  
 Для использования команды OLE DB может возвратить несколько результатов укажите [CMultipleResults](../../data/oledb/cmultipleresults-class.md).  В противном случае используйте [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md).  Дополнительные сведения см. в разделе [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx).  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[Закрыть](../Topic/CCommand::Close.md)|Закрывает текущую команду.|  
|[GetNextResult](../Topic/CCommand::GetNextResult.md)|Получить следующий результат при использовании несколько результирующих наборов.|  
|[Откройте .](../../data/oledb/ccommand-open.md)|Выполняется и при необходимости привязывает команду.|  
  
### Методы Inherited  
  
|||  
|-|-|  
|[Create](../../data/oledb/ccommand-create.md)|Создает новую команду для указанного сеанса, затем задает текст команды.|  
|[CreateCommand](../Topic/CCommand::CreateCommand.md)|Создает новую команду.|  
|[GetParameterInfo](../Topic/CCommand::GetParameterInfo.md)|Получает список параметров команды, их имена и их типов.|  
|[Подготовка](../../data/oledb/ccommand-prepare.md)|Проверяет и оптимизирует текущую команду.|  
|[ReleaseCommand](../Topic/CCommand::ReleaseCommand.md)|Выпуски доступ параметра при необходимости, затем выпуски команду.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|Определяет собственный тип каждого параметра команды.|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|Отменяет текущий план выполнения команды.|  
  
## Заметки  
 Используйте этот класс при выполнении команды или операции, основанной на параметрах.  Если необходимо просто следует открыть простой набор строк, следует использовать [CTable](../../data/oledb/ctable-class.md).  
  
 Класс доступа используется определяет метод параметров и данные привязки.  
  
 Обратите внимание, что нельзя использовать хранимые процедуры с поставщиком OLE DB для jet, поскольку этот поставщик не поддерживает хранимые процедуры \(только константы недопустимы в строках запроса\).  
  
## Требования  
 **Header:**  atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)