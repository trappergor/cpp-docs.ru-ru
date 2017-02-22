---
title: "IDBSchemaRowsetImpl::GetSchemas | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IDBSchemaRowsetImpl::GetSchemas"
  - "GetSchemas"
  - "IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "ATL.IDBSchemaRowsetImpl.GetSchemas"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "IDBSchemaRowsetImpl.GetSchemas"
  - "IDBSchemaRowsetImpl::GetSchemas"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSchemas - метод"
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBSchemaRowsetImpl::GetSchemas
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).  
  
## Синтаксис  
  
```  
  
STDMETHOD  
( GetSchema s )(  
   ULONG *   
pcSchemas  
,  
   GUID **   
prgSchemas  
,  
   ULONG**   
prgRest  
);  
  
```  
  
#### Параметры  
 *pcSchemas*  
 \[выходные данные\] Указатель на **ULONG**, заполняемый количеством схем.  
  
 *prgSchemas*  
 \[выходные данные\] Указатель на массив идентификаторов GUID, который заполняется указателем на массив идентификаторов GUID набора строк схемы.  
  
 *prgRest*  
 \[выходные данные\] Указатель на массив **ULONG**, который должен быть заполнен массивом ограничений.  
  
## Заметки  
 Этот метод возвращает массив всех наборов строк схемы, поддерживаемых поставщиком. См. [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Для реализаций этой функции пользователь должен иметь карту схемы в классе сеанса. Затем с помощью сведений о карте схемы выдается массив идентификаторов GUID для схемы на карте. Он представляет схемы, поддерживаемые поставщиком.  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ru-ru/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [Классы схемы Rowset и Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)