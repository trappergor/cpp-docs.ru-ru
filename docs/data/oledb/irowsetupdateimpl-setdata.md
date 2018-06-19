---
title: IRowsetUpdateImpl::SetData | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
dev_langs:
- C++
helpviewer_keywords:
- SetData method
ms.assetid: 7288a8d1-a7cf-4957-b832-0f3b18fd0da4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: adb15394f4470e23c0ecec2e704829c973c7f3a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103672"
---
# <a name="irowsetupdateimplsetdata"></a>IRowsetUpdateImpl::SetData
Задает значения данных в одном или нескольких столбцах.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetChange::SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Этот метод переопределяет [IRowsetChangeImpl::SetData](../../data/oledb/irowsetchangeimpl-setdata.md) метод но включает кэширование исходных данных для немедленно обновляемых подписок или Отложенная обработка операции разрешения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)