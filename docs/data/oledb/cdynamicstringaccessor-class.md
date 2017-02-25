---
title: "Класс CDynamicStringAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessor - класс"
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс CDynamicStringAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет получить доступ к источнику данных, когда неизвестна схема базы данных \(базовая структура\).  
  
## Синтаксис  
  
```  
  
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[GetString](../Topic/CDynamicStringAccessor::GetString.md)|Извлекает указанные данные столбца в виде строки.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|Задает указанные данные столбца в виде строки.|  
  
## Заметки  
 Пока данные запросов [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) в собственном формате сообщили поставщиком, запросы `CDynamicStringAccessor`, выборка поставщика все данные, получаемые доступ из хранилища данных в виде строковых данных.  Это особенно удобно для простых заданий, которые не требуют подсчета значений в хранилище данных, таких как отображение или распечатка содержимого хранилища данных.  
  
 Собственный тип данных столбца в хранилище данных не имеет значения; если поставщик может поддерживать преобразование данных, оно будет предоставлять данные в формате строки.  Если поставщик не поддерживает преобразование из собственного типа данных в строке \(которая не общая\), запрашивающий вызов возвращает успех значение **DB\_S\_ERRORSOCCURED**, а состояние для соответствующего столбца в проблему преобразования с **DBSTATUS\_E\_CANTCONVERTVALUE**.  
  
 Используйте методы `CDynamicStringAccessor` для получения информации о столбцах.  Информация о столбцах используется для динамического создания метода доступа во время выполнения.  
  
 Информация о столбцах хранится в буфере, созданном и управляемым данным классом.  Получение данных из буфера с помощью [GetString](../Topic/CDynamicStringAccessor::GetString.md) или сохранить ее в буфере с помощью [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
 Обсуждение и примеры использования классов методов доступа см. в разделе [Использование динамических методов доступа](../../data/oledb/using-dynamic-accessors.md).  
  
## Требования  
 **Заголовок**: atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../Topic/CAccessor%20Class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../Topic/CManualAccessor%20Class.md)   
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)   
 [Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [Класс CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)