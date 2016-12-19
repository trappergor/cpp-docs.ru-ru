---
title: "IDBSchemaRowsetImpl::SetRestrictions | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl::SetRestrictions"
  - "SetRestrictions"
  - "IDBSchemaRowsetImpl.SetRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetRestrictions - метод"
ms.assetid: 707d5065-b853-4d38-9b67-3066b4d3b279
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::SetRestrictions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.  
  
## Синтаксис  
  
```  
  
void SetRestrictions(  
   ULONG   
cRestrictions  
,  
   GUID* /*   
rguidSchema  
*/,  
   ULONG*   
rgRestrictions  
);  
  
```  
  
#### Параметры  
 `cRestrictions`  
 \[входные данные\] Число ограничений в массиве `rgRestrictions` и число GUID в массиве `rguidSchema`.  
  
 `rguidSchema`  
 \[входные данные\] Массив GUID наборов строк схемы, для которого требуется извлечь ограничения. Каждый элемент массива содержит GUID одного набора строк схемы \(например, `DBSCHEMA_TABLES`\).  
  
 `rgRestrictions`  
 \[входные данные\] Массив длиной `cRestrictions` для задаваемых значений ограничений. Каждый элемент соответствует ограничениям в наборе строк схемы, определяемом по GUID. Если набор строк схемы не поддерживается поставщиком, элементу присваивается нулевое значение. В противном случае значение **ULONG** значение содержит битовую маску, которая представляет ограничения, поддерживаемые в этом наборе строк схемы. Дополнительные сведения о том, какие ограничения соответствуют определенному набору строк схемы, см. в таблице GUID наборов строк схем в подразделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *справочнике программиста OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Заметки  
 Объект **IDBSchemaRowset** вызывает `SetRestrictions` для определения ограничений, поддерживаемых в определенном наборе строк схемы \(вызывается с помощью [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) через повышенный указатель\). Ограничения позволяют выбирать только совпадающие строки \(например, поиск всех столбцов в таблице MyTable\). Ограничения являются необязательными, и если не поддерживается ни одно ограничение \(по умолчанию\), всегда возвращаются все данные.  
  
 Реализация по умолчанию этого метода задает элементы массива `rgRestrictions` равными 0. Чтобы задать ограничения, отличные от используемых по умолчанию, нужно переопределить установку по умолчанию в классе сеанса.  
  
 Сведения о реализации поддержки наборов строк схемы см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).  
  
 Пример поставщика, поддерживающего наборы строк схемы, см. в примере [UpdatePV](../../top/visual-cpp-samples.md).  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *справочнике программиста OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ru-ru/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Классы схемы Rowset и Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)   
 [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md)   
 [UpdatePV](../../top/visual-cpp-samples.md)