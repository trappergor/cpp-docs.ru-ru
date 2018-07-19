---
title: CRowset::GetApproximatePosition | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRowset::GetApproximatePosition
- ATL::CRowset<TAccessor>::GetApproximatePosition
- CRowset.GetApproximatePosition
- CRowset::GetApproximatePosition
- GetApproximatePosition
- ATL.CRowset.GetApproximatePosition
- CRowset<TAccessor>::GetApproximatePosition
dev_langs:
- C++
helpviewer_keywords:
- GetApproximatePosition method
ms.assetid: 8f9ccd41-0590-468e-b202-6731d0f99d21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 882d35fae9e352c99a534dc634f105a9b9a35664
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098372"
---
# <a name="crowsetgetapproximateposition"></a>CRowset::GetApproximatePosition
Возвращает приблизительное позицию строка, соответствующая закладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetApproximatePosition(const CBookmarkBase* pBookmark,   
   DBCOUNTITEM* pPosition,   
   DBCOUNTITEM* pcRows) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `pBookmark`  
 [in] Указатель на закладку, определяющий строку, позиция которого может быть найден. **Значение NULL** если только количество строк не требуется.  
  
 *pPosition*  
 [out] Указатель на расположение, где `GetApproximatePosition` возвращает позицию строки. **Значение NULL** если позиция не требуется.  
  
 `pcRows`  
 [out] Указатель на расположение, где `GetApproximatePosition` возвращает общее число строк. **Значение NULL** Если число строк не является обязательным.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод требует дополнительный интерфейс `IRowsetScroll`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetScroll** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
 Сведения об использовании закладки в потребителей в разделе [с помощью закладок](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [IRowsetScroll::GetApproximatePosition](https://msdn.microsoft.com/en-us/library/ms712901.aspx)