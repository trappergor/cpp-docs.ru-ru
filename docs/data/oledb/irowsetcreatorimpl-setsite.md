---
title: "IRowsetCreatorImpl::SetSite | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
dev_langs:
- C++
helpviewer_keywords:
- SetSite method
ms.assetid: e92e63d5-93e4-4ee0-9ef7-bb6583cc8091
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57d5a2027203c912ff004d7f4dcce0d23724b233
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetcreatorimplsetsite"></a>IRowsetCreatorImpl::SetSite
Задает сайт, который содержит объект набора строк. Дополнительные сведения см. в разделе [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(SetSite )(IUnknown* pCreator);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pCreator`  
 [in] Указатель на **IUnknown** указатель интерфейса узла Управление объекта набора строк.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Кроме того `IRowsetCreatorImpl::SetSite` позволяет OLE DB **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS** свойства.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)