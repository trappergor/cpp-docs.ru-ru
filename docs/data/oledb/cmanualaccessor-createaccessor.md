---
title: "CManualAccessor::CreateAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs: C++
helpviewer_keywords: CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9bbd82a7ab2720d63ffa7860c26fc447b58e4f24
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
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