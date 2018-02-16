---
title: "CManualAccessor::CreateAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs:
- C++
helpviewer_keywords:
- CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d066bec37955d39ecee1fdca5522df843c84442
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT CreateAccessor(int nBindEntries,   
  void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nBindEntries`  
 [in] Число столбцов. Это число должно совпадать с числом вызовов [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) функции.  
  
 `pBuffer`  
 [in] Указатель на буфер, где хранятся выходных столбцов.  
  
 `nBufferSize`  
 [in] Размер буфера в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 Эта функция вызывается перед вызовом метода `CManualAccessor::AddBindEntry` функции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [Образец DBViewer](../../visual-cpp-samples.md)