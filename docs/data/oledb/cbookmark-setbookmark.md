---
title: CBookmark::SetBookmark | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
dev_langs:
- C++
helpviewer_keywords:
- SetBookmark method
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d8f4402a6caf01f4d813e6ee8f9fd2d95512394
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093681"
---
# <a name="cbookmarksetbookmark"></a>CBookmark::SetBookmark
Копирует значение ссылается `pBuffer` для `CBookmark` буфер и задает размер буфера `nSize`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT SetBookmark(DBLENGTH nSize,  
  BYTE* pBuffer) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *nSize*  
 [in] Размер буфера закладки.  
  
 `pBuffer`  
 [in] Указатель на массив байтов, содержащий значение закладки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Эта функция доступна только в **CBookmark\<0 >**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CBookmark](../../data/oledb/cbookmark-class.md)