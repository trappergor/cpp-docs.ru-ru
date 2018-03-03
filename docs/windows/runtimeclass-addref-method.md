---
title: "Метод RuntimeClass::AddRef | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method
ms.assetid: 9c705749-680b-4308-bbec-5b601e8e7dbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73f5a9a458e74d782491d3896f431f765bde87fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassaddref-method"></a>Метод RuntimeClass::AddRef
Увеличивает счетчик ссылок для текущего объекта RuntimeClass.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)