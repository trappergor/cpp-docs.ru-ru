---
title: "Класс IRowsetIdentityImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
dev_langs: C++
helpviewer_keywords: IRowsetIdentityImpl class
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cef373c7ddafe17a7843f8559588d5f0da9ee270
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetidentityimpl-class"></a>Класс IRowsetIdentityImpl
Реализует OLE DB [IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx) интерфейс, который позволяет тестировать для идентификации строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IRowsetIdentityImpl`.  
  
 `RowClass`  
 Устройство хранения для **HROW**.  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[IsSameRow](../../data/oledb/irowsetidentityimpl-issamerow.md)|Сравнивает два дескрипторы строк для просмотра, если они ссылаются на той же строке.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)