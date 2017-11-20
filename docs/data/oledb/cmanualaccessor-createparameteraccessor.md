---
title: "CManualAccessor::CreateParameterAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
dev_langs: C++
helpviewer_keywords: CreateParameterAccessor method
ms.assetid: d0a2095b-b37c-4472-accc-45ef365a18c8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 94fbe6e0a7e44e861c3a0cb0039860e47a27ad3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cmanualaccessorcreateparameteraccessor"></a>CManualAccessor::CreateParameterAccessor
Выделяет память для параметра bind структуры и инициализирует параметризованные члены данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT CreateParameterAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nBindEntries`  
 [in] Число столбцов.  
  
 `pBuffer`  
 [in] Указатель на буфер, в которой хранятся входные столбцы.  
  
 `nBufferSize`  
 [in] Размер буфера в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
## <a name="remarks"></a>Примечания  
 Перед вызовом этой функции необходимо вызвать [AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)   
 [CManualAccessor::AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)