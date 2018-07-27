---
title: Метод Module::CREATE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99ede64c239909956f1f767db34a2a6a14c02314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874893"
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

 