---
title: "IDBSchemaRowsetImpl::CheckRestrictions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CheckRestrictions"
  - "IDBSchemaRowsetImpl::CheckRestrictions"
  - "IDBSchemaRowsetImpl.CheckRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckRestrictions - метод"
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBSchemaRowsetImpl::CheckRestrictions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет допустимость ограничений относительно набора строк схемы.  
  
## Синтаксис  
  
```  
  
HRESULT CheckRestrictions(  
   REFGUID   
rguidSchema  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[]  
);  
  
```  
  
#### Параметры  
 `rguidSchema`  
 \[входные данные\] Ссылка на запрошенный GUID набора строк схемы \(например, `DBSCHEMA_TABLES`\).  
  
 `cRestrictions`  
 \[входные данные\] Число ограничений, переданных потребителем для набора строк схемы.  
  
 `rgRestrictions`  
 \[входные данные\] Массив длиной *cRestrictions* для задаваемых значений ограничений. Дополнительные сведения см. в описании параметра `rgRestrictions` в [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
## Заметки  
 Используйте `CheckRestrictions` для проверки допустимости ограничений для набора строк схемы. Он проверяет ограничения для наборов строк схемы `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** и **DBSCHEMA\_PROVIDER\_TYPES**. Вызовите для определения правильности вызова **IDBSchemaRowset::GetRowset**. Если необходима поддержка наборов строк схемы, отличных от перечисленных выше, создайте собственную функцию для выполнения этой задачи.  
  
 `CheckRestrictions` определяет, вызывает ли потребитель [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) с правильным ограничением и правильным типом ограничения \(например, `VT_BSTR` для строки\), поддерживаемыми поставщиком. Он также определяет, поддерживается ли правильное количество ограничений. По умолчанию `CheckRestrictions` будет обращаться к поставщику через вызов [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md), ограничения которого он поддерживает в заданном наборе строк. Затем он сравнит ограничения от потребителя с ограничениями, поддерживаемыми поставщиком. Результатом будет успешное или неудачное выполнение.  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *справочнике программиста OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ru-ru/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Классы схемы Rowset и Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)