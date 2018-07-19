---
title: CEnumerator::Find | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs:
- C++
helpviewer_keywords:
- Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2466127dab53fa6646a4f149400e4318aed59970
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094486"
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
Ищет указанное имя среди доступных поставщиков.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      bool Find(TCHAR* szSearchName) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *szSearchName*  
 [in] Имя для поиска.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** найденные имя. в противном случае **false**.  
  
## <a name="remarks"></a>Примечания  
 Это имя соответствует **SOURCES_NAME** членом [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CEnumerator](../../data/oledb/cenumerator-class.md)