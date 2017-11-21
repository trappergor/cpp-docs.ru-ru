---
title: "Метод AsyncBase::Cancel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::Cancel
dev_langs: C++
helpviewer_keywords: Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5b6215c871da92087a7555bfb5a97f48d60223de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasecancel-method"></a>Метод AsyncBase::Cancel
Отменяет асинхронную операцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 По умолчанию всегда возвращает значение S_OK.  
  
## <a name="remarks"></a>Примечания  
 Cancel() — это реализация по умолчанию IAsyncInfo::Cancel, а не фактический работает. Действительно отменить асинхронную операцию, переопределите OnCancel() чисто виртуального метода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)