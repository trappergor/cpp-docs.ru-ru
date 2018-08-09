---
title: Метод Module::CREATE | Документация Майкрософт
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
ms.openlocfilehash: 1b3f865addd83bec64250807285947ea1c92e59f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016617"
---
# <a name="modulecreate-method"></a>Метод Module::Create
Создает экземпляр модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
### <a name="parameters"></a>Параметры  
 *T*  
 Тип модуля.  
  
 *обратный вызов*  
 Вызывается при освобождении последнего объекта экземпляр модуля.  
  
 *object*  
 *Объект* и *метод* параметры используются в сочетании. Указывает на последний объект экземпляра при освобождении последнего объекта экземпляра в модуле.  
  
 *Метод*  
 *Объект* и *метод* параметры используются в сочетании. Указывает метод последнего экземпляра объекта при освобождении последнего объекта экземпляра в модуле.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на модуль.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
[Класс Module](../windows/module-class.md)