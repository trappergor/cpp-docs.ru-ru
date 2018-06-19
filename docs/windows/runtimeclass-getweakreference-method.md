---
title: Метод RuntimeClass::GetWeakReference | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs:
- C++
helpviewer_keywords:
- GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e49703e96728e7287206aa264ce12deaad611495
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888223"
---
# <a name="runtimeclassgetweakreference-method"></a>Метод RuntimeClass::GetWeakReference
Возвращает указатель на объект слабой ссылки для текущего объекта RuntimeClass.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
#### <a name="parameters"></a>Параметры  
 `weakReference`  
 После завершения операции представляет указатель на объект слабой ссылки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)