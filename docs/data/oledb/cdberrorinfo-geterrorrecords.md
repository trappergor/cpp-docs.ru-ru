---
title: CDBErrorInfo::GetErrorRecords | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- GetErrorRecords method
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 33e0ab54bc3da570aecba0df347e14a511b0a833
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdberrorinfogeterrorrecords"></a>CDBErrorInfo::GetErrorRecords
Возвращает записи об ошибках для указанного объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords) throw();  


HRESULT GetErrorRecords(ULONG* pcRecords) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *pUnk*  
 [in] Интерфейс к объекту, для которого необходимо получить записи об ошибках.  
  
 `iid`  
 [in] Идентификатор IID интерфейса, с которым связана ошибка.  
  
 *pcRecords*  
 [out] Указатель на количество записей ошибок (единицы).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Если вы хотите проверить интерфейс, который нужно получить сведения об ошибке из, используйте первую форму функции. В противном случае следует используйте вторую форму.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)