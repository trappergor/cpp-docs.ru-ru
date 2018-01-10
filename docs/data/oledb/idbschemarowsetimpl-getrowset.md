---
title: "IDBSchemaRowsetImpl::GetRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
dev_langs: C++
helpviewer_keywords: GetRowset method
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5164bcd56c61868649af6185c8b84ebf20098b18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimplgetrowset"></a>IDBSchemaRowsetImpl::GetRowset
Возвращает набор строк схемы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD (GetRowset)(  
   IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pUnkOuter`  
 [входные данные] Внешний **IUnknown** при агрегировании; в противном случае — **NULL**.  
  
 `rguidSchema`  
 [входные данные] Ссылка на запрошенный GUID набора строк схемы (например, `DBSCHEMA_TABLES`).  
  
 `cRestrictions`  
 [входные данные] Число ограничений, применяемых к набору строк.  
  
 `rgRestrictions`  
 [входные данные] Массив типов `cRestrictions`**VARIANT**, которые представляют ограничения.  
  
 `riid`  
 [входные данные] IID для запроса созданного набора строк схемы.  
  
 `cPropertySets`  
 [входные данные] Число задаваемых наборов свойств.  
  
 `rgPropertySets`  
 [входные/выходные данные] Массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) , задаваемых в созданном наборе строк схемы.  
  
 `ppRowset`  
 [выходные данные] Указатель на запрошенный интерфейс в созданном наборе строк схемы.  
  
## <a name="remarks"></a>Примечания  
 Для реализаций этого метода пользователь должен иметь карту схемы в классе сеанса. С помощью сведений о карте схемы `GetRowset` создает заданный объект набора строк, если параметр `rguidSchema` равен одному из GUID карты записей. Описание карты записей см. в разделе [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) .  
  
 В разделе [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [Класс IDBSchemaRowsetImpl члены](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)