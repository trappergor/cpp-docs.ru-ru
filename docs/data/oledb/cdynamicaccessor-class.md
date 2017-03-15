---
title: "Класс CDynamicAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicAccessor"
  - "ATL::CDynamicAccessor"
  - "CDynamicAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicAccessor - класс"
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс CDynamicAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет получить доступ к источнику данных, когда неизвестна схема базы данных \(базовая структура\).  
  
## Синтаксис  
  
```  
class CDynamicAccessor : public CAccessorBase  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|Добавляет запись привязки к выходным столбцам предоставляет доступ по умолчанию.|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|Создает и инициализирует объект `CDynamicAccessor`.|  
|[Закрыть](../../data/oledb/cdynamicaccessor-close.md)|Unbinds все столбцы, выпуски выделяемая память и выпуски указатель интерфейса [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) в классе.|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|Извлекает закладки для текущей строки.|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|Извлекает БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ обработки значение для текущей строки.|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|Возвращает максимальный размер БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА в байтах.|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|Возвращает число столбцов в наборе строк.|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|Извлекает характеристики столбца.|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|Извлекает метаданные столбца.|  
|[GetColumnName](../Topic/CDynamicAccessor::GetColumnName.md)|Получает имя указанного столбца.|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|Возвращает тип данных выбранного столбца.|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|Извлекает максимальная возможная длина столбца в байтах.|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|Извлекает индекс столбца заданное имя столбца.|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|Извлекает состояние выбранного столбца.|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|Извлекает данные из буфера.|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|Задает БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ обработки значение для текущей строки.|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|Задает максимальный размер БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА в байтах.|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|Задает длину столбца в байтах.|  
|[SetStatus](../Topic/CDynamicAccessor::SetStatus.md)|Задает состояние выбранного столбца.|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|Сохраняет данные в буфер.|  
  
## Заметки  
 Используйте методы `CDynamicAccessor` для получения информации о столбцах, таких как имена столбцов, число столбцов, тип данных и т д  После этого используется эта информация о столбцах используется для динамического создания метода доступа во время выполнения.  
  
 Информация о столбцах хранится в буфере, созданном и управляемым данным классом.  Получение данных из буфера с помощью [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
 Обсуждение и примеры использования классов методов доступа см. в разделе [Использование динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).  
  
## Требования  
 **Заголовок**: atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../Topic/CAccessor%20Class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../Topic/CManualAccessor%20Class.md)