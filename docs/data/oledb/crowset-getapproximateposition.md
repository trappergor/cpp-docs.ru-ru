---
title: "CRowset::GetApproximatePosition | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset::GetApproximatePosition
- ATL::CRowset<TAccessor>::GetApproximatePosition
- CRowset.GetApproximatePosition
- CRowset::GetApproximatePosition
- GetApproximatePosition
- ATL.CRowset.GetApproximatePosition
- CRowset<TAccessor>::GetApproximatePosition
dev_langs: C++
helpviewer_keywords: GetApproximatePosition method
ms.assetid: 8f9ccd41-0590-468e-b202-6731d0f99d21
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 86d6e17c3bfe01cc579e9a0afab8f555419e5116
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetgetapproximateposition"></a>CRowset::GetApproximatePosition
Возвращает приблизительное позицию строка, соответствующая закладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT GetApproximatePosition(   
   const CBookmarkBase* pBookmark,   
   DBCOUNTITEM* pPosition,   
   DBCOUNTITEM* pcRows    
) throw( );  
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