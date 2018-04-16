---
title: Метод Module::CREATE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e566b34140c0b82072c8469cd8d965f807e244ec
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="modulecreate-method"></a>Метод Module::Create
Создает экземпляр модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW static Module& Create();  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип модуля.  
  
 `callback`  
 Вызывается при освобождении последнего объекта экземпляр модуля.  
  
 `object`  
 `object` И `method` параметры используются в сочетании. Указывает на последний объект экземпляра при освобождении последнего объекта экземпляра в модуле.  
  
 `method`  
 `object` И `method` параметры используются в сочетании. Указывает метод последнего экземпляра объекта при освобождении последнего объекта экземпляра в модуле.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на модуль.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
[Класс Module](../windows/module-class.md)

 