---
title: "Метод RuntimeClass::Release | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::Release
dev_langs: C++
helpviewer_keywords: Release method
ms.assetid: 0bd6f9e2-ad90-4de6-adef-a6286f458cb6
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b989b32add712a9f9c97385104ed65a5cc704c9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclassrelease-method"></a>Метод RuntimeClass::Release
Выполняет операцию освобождения модели COM, с текущим объектом RuntimeClass.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Если счетчик ссылок становится равным нулю, RuntimeClass объект удаляется.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)