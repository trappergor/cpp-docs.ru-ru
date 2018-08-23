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
ms.openlocfilehash: 9ae4f50e6d2d614e444766babf8e55f5c9f83932
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609548"
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