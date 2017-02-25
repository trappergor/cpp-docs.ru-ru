---
title: "Класс IDBSchemaRowsetImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBSchemaRowsetImpl - класс"
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Класс IDBSchemaRowsetImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет реализацию для наборов строк схемы.  
  
## Синтаксис  
  
```  
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### Параметры  
 `SessionClass`  
 Класс, по которому наследуется `IDBSchemaRowsetImpl`. Как правило, этот класс будет классом сеанса пользователя.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|Проверяет допустимость ограничений относительно набора строк схемы.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|Реализует функцию создателя COM\-объекта для объекта, указанного параметром шаблона.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.|  
  
### Методы интерфейса  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|Возвращает набор строк схемы.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|  
  
## Заметки  
 Этот класс реализует интерфейс [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) и шаблонизируемую функцию создателя [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB использует наборы строк схемы для возврата сведений о данных в поставщике. Такие данные часто называют метаданными. По умолчанию поставщик всегда должен поддерживать `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** и **DBSCHEMA\_PROVIDER\_TYPES**, как описано в разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *справочнике программиста OLE DB*. Наборы строк схемы назначаются в карте схемы. Сведения о карте записей схемы см. в разделе [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md).  
  
 Мастер поставщиков OLE DB в мастере объектов ATL автоматически создает код для наборов строк схемы в проекте. \(По умолчанию мастер поддерживает упомянутые выше обязательные наборы строк схемы.\) При создании потребителя мастер объектов ATL использует наборы строк схемы для привязки правильных данных к поставщику. Если наборы строк схемы не реализованы для представления правильных метаданных, мастер не выполнит привязку правильных данных.  
  
 Сведения о поддержке наборов строк схемы в поставщике см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [Наборы строк схемы](https://msdn.microsoft.com/en-us/library/ms712921.aspx) в *справочнике программиста OLE DB*.  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ru-ru/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Классы схемы Rowset и Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)   
 [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md)