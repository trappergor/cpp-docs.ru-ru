---
title: "CDynamicParameterAccessor::CDynamicParameterAccessor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
dev_langs: C++
helpviewer_keywords:
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
ms.assetid: a1cce5e4-dfb9-43a2-bfb8-0435c653674a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e08c26c7ba9d07c5e845aea3443c824498354b74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a>CDynamicParameterAccessor::CDynamicParameterAccessor
Конструктор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor( eBlobHandling, nBlobSize )  
```  
  
#### <a name="parameters"></a>Параметры  
 `eBlobHandling`  
 Указывает способ обработки данных больших двоичных ОБЪЕКТОВ. Значение по умолчанию — **DBBLOBHANDLING_DEFAULT**. В разделе [CDynamicAccessor::SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) описание **DBBLOBHANDLINGENUM** значения.  
  
 `nBlobSize`  
 Максимальный размер большого двоичного ОБЪЕКТА в байтах; столбец данных через это значение рассматривается как большой двоичный объект. Значение по умолчанию — 8000. В разделе [CDynamicAccessor::SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) подробные сведения.  
  
## <a name="remarks"></a>Примечания  
 В разделе [CDynamicAccessor::CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) конструктор Дополнительные сведения об обработке большого двоичного ОБЪЕКТА.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)