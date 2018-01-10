---
title: "Класс CDynamicStringAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDynamicStringAccessor
dev_langs: C++
helpviewer_keywords: CDynamicStringAccessor class
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d6c24e6eaac83d72f8710b039b312f40517fd7e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicstringaccessor-class"></a>Класс CDynamicStringAccessor
Дает возможность доступа к источнику данных, если у вас нет сведений о схеме базы данных (базовая структура).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|Возвращает данные указанного столбца как строка.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|Задает данные указанного столбца в виде строки.|  
  
## <a name="remarks"></a>Примечания  
 Хотя [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) запрашивает данные в собственном формате, полученных от поставщика `CDynamicStringAccessor` запросов, что поставщик извлечь все данные из хранилища данных в виде строковых данных. Это особенно полезно для простых задач, не требующих вычисления значений в хранилище данных, таких как отображение или Печать содержимого хранилища данных.  
  
 Собственный тип данных столбца в хранилище данных не имеет значения; при условии, что поставщик поддерживает преобразование данных, он будет предоставлять данные в строковом формате. Если поставщик не поддерживает преобразование из собственного типа данных в строку (которая не является распространенным), запрашивающего вызов вернет значение success **DB_S_ERRORSOCCURED**, и состояние для соответствующего столбца будет Указывает на проблему преобразования с **DBSTATUS_E_CANTCONVERTVALUE**.  
  
 Используйте `CDynamicStringAccessor` методов, чтобы получить сведения о столбцах. Используйте эти сведения для столбца для динамического создания метода доступа во время выполнения.  
  
 Сведения о столбце хранится в буфере, созданном и управляемым данным классом. Получить данные из буфера с помощью [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), и не сохраняет буфер с помощью [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
 Обсуждение и примеры использования классов динамического метода доступа см. в разделе [использование динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:**atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-класс](../../data/oledb/caccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)   
 [Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [Класс CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)