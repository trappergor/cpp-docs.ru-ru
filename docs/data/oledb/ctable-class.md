---
title: "Класс CTable | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
dev_langs:
- C++
helpviewer_keywords:
- CTable class
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59723cef5a2c0c74d0bcb5382d683f27b0f548fe
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="ctable-class"></a>Класс CTable
Предоставляет средства для прямого доступа к простому набору строк (без параметров).  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CNoAccessor, 
            template <typename T> class TRowset = CRowset>  
class CTable :  
   public CAccessorRowset <TAccessor, TRowset>  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Класса метода доступа.  
  
 `TRowset`  
 От класса набора строк.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Открыть](../../data/oledb/ctable-open.md)|Открытие таблицы.|  
  
## <a name="remarks"></a>Примечания  
 В разделе [CCommand](../../data/oledb/ccommand-class.md) сведения о том, как выполнить команду, чтобы доступ к строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)