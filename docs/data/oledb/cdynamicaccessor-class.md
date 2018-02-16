---
title: "Класс CDynamicAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eb9bd08cb51a90f2bd616efcace8a66625e66827
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessor-class"></a>Класс CDynamicAccessor
Дает возможность доступа к источнику данных, если у вас нет сведений о схеме базы данных (базовая структура).  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDynamicAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|Добавляет запись привязку выходных столбцов, переопределяя метод доступа по умолчанию.|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|Создает и инициализирует `CDynamicAccessor` объекта.|  
|[Закрыть](../../data/oledb/cdynamicaccessor-close.md)|Отменяет привязку всех столбцов, освобождает выделенной памяти и освобождает [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) указатель интерфейса в классе.|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|Извлекает закладки для текущей строки.|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|Извлекает большой двоичный объект, обработки значения для текущей строки.|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|Получает максимальный размер большого двоичного ОБЪЕКТА в байтах.|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|Возвращает число столбцов в наборе строк.|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|Извлекает характеристики столбца.|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|Извлекает метаданные столбца.|  
|[GetColumnName](../../data/oledb/cdynamicaccessor-getcolumnname.md)|Возвращает имя указанного столбца.|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|Получает тип данных указанного столбца.|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|Получает максимально возможная длина столбца в байтах.|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|Возвращает индекс столбца, заданному имени столбца.|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|Получает состояние указанного столбца.|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|Извлекает данные из буфера.|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|Задает больших двоичных ОБЪЕКТОВ, обработки значения для текущей строки.|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|Задает максимальный размер большого двоичного ОБЪЕКТА в байтах.|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|Задает длину столбца в байтах.|  
|[SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)|Задает состояние указанного столбца.|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|Сохраняет данные в буфер.|  
  
## <a name="remarks"></a>Примечания  
 Используйте `CDynamicAccessor` методов, чтобы получить сведения о столбцах, таких как имена столбцов, число столбцов, тип данных и т. д. Выполните эти данные столбца для динамического создания метода доступа во время выполнения.  
  
 Сведения о столбце хранится в буфере, который создается и управляется этим классом. Получить данные из буфера с помощью [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).  
  
 Обсуждение и примеры использования классов динамического метода доступа см. в разделе [использование динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:**atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-класс](../../data/oledb/caccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)