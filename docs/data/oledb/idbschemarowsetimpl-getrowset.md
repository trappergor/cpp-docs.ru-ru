---
title: "IDBSchemaRowsetImpl::GetRowset | Microsoft Docs"
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
  - "ATL::IDBSchemaRowsetImpl::GetRowset"
  - "ATL.IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl::GetRowset"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "GetRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowset - метод"
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::GetRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает набор строк схемы.  
  
## Синтаксис  
  
```  
  
STDMETHOD (GetRowset)(  
   IUnknown *  
pUnkOuter  
,  
   REFGUID   
rguidSchema  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[],  
   REFIID   
riid  
,  
   ULONG   
cPropertySets  
,  
   DBPROPSET   
rgPropertySets  
[],  
   IUnknown **  
ppRowset  
);  
  
```  
  
#### Параметры  
 `pUnkOuter`  
 \[входные данные\] Внешний **IUnknown** при агрегировании; в противном случае — **NULL**.  
  
 `rguidSchema`  
 \[входные данные\] Ссылка на запрошенный GUID набора строк схемы \(например, `DBSCHEMA_TABLES`\).  
  
 `cRestrictions`  
 \[входные данные\] Число ограничений, применяемых к набору строк.  
  
 `rgRestrictions`  
 \[входные данные\] Массив типов `cRestrictions` **VARIANT**, которые представляют ограничения.  
  
 `riid`  
 \[входные данные\] IID для запроса созданного набора строк схемы.  
  
 `cPropertySets`  
 \[входные данные\] Число задаваемых наборов свойств.  
  
 `rgPropertySets`  
 \[входные\/выходные данные\] Массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), задаваемых в созданном наборе строк схемы.  
  
 `ppRowset`  
 \[выходные данные\] Указатель на запрошенный интерфейс в созданном наборе строк схемы.  
  
## Заметки  
 Для реализаций этого метода пользователь должен иметь карту схемы в классе сеанса. С помощью сведений о карте схемы `GetRowset` создает заданный объект набора строк, если параметр `rguidSchema` равен одному из GUID карты записей. Описание карты записей см. в разделе [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md).  
  
 См. [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx) в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ru-ru/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [Классы схемы Rowset и Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)