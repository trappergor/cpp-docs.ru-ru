---
title: "IDBSchemaRowsetImpl::GetSchemas | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs:
- C++
helpviewer_keywords:
- GetSchemas method
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55ccad037b072e4d731462bbf89ff48b186bf068
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="idbschemarowsetimplgetschemas"></a>IDBSchemaRowsetImpl::GetSchemas
Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (GetSchema s )(ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest);  
```  
  
#### <a name="parameters"></a>Параметры  
 *pcSchemas*  
 [выходные данные] Указатель на **ULONG** , заполняемый количеством схем.  
  
 *prgSchemas*  
 [выходные данные] Указатель на массив идентификаторов GUID, который заполняется указателем на массив идентификаторов GUID набора строк схемы.  
  
 *prgRest*  
 [выходные данные] Указатель на массив **ULONG**, который должен быть заполнен массивом ограничений.  
  
## <a name="remarks"></a>Примечания  
 Этот метод возвращает массив всех наборов строк схемы, поддерживаемых поставщиком. В разделе [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) в Windows SDK.  
  
 Для реализаций этой функции пользователь должен иметь карту схемы в классе сеанса. Затем с помощью сведений о карте схемы выдается массив идентификаторов GUID для схемы на карте. Он представляет схемы, поддерживаемые поставщиком.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [Класс IDBSchemaRowsetImpl члены](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [Классы Rowset и Typedef схемы](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)