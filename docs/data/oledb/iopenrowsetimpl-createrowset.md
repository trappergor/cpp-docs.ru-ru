---
title: "IOpenRowsetImpl::CreateRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
dev_langs: C++
helpviewer_keywords: CreateRowset method
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ada7e23a3ff48ea9b97263c8fa94a7970185f7a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iopenrowsetimplcreaterowset"></a>IOpenRowsetImpl::CreateRowset
Создает объект набора строк. Не вызывается непосредственно пользователем. В разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) в *справочника программиста OLE DB.*  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `RowsetClass`  
 Член класса шаблона, представляющий пользователя класса набора строк. Как правило, создаются с помощью мастера.  
  
 `pRowsetObj`  
 [out] Указатель на объект набора строк. Обычно этот параметр не используется, но он может использоваться, если в наборе строк, необходимо выполнить дополнительные действия до его передачи в COM-объект. Время существования `pRowsetObj` , ограничивается `ppRowset`.  
  
 Другие параметры в разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) в *Справочник программиста OLE DB.*  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)