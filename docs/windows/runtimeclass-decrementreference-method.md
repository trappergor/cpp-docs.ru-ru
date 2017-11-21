---
title: "Метод RuntimeClass::DecrementReference | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::DecrementReference
dev_langs: C++
ms.assetid: f5ecfeaa-2865-455b-9208-94a0685fd2c6
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b39467f9e718cece5fe7505bee0148bac9bf2067
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclassdecrementreference-method"></a>Метод RuntimeClass::DecrementReference
Уменьшает счетчик ссылок для текущего объекта RuntimeClass.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ULONG DecrementReference();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)