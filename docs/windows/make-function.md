---
title: Функция Make | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
dev_langs:
- C++
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8b02b51dca4ae3712274b2b011c1967e5006637
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422406"
---
# <a name="make-function"></a>Функция Make

Инициализирует указанный класс среды выполнения Windows. Используйте эту функцию, чтобы создать экземпляр компонента, который определен в том же модуле.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8,
   TArg9 &&arg9
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3
);
template <
   typename T,
   typename TArg1,
   typename TArg2
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2
);
template <
   typename T,
   typename TArg1
>
ComPtr<T> Make(
   TArg1 &&arg1
);
template <
   typename T
>
ComPtr<T> Make();
```

### <a name="parameters"></a>Параметры

*T*<br/>
Определяемый пользователем класс, наследуемый от `WRL::RuntimeClass`.

*TArg1*<br/>
Тип аргумента 1, который передается в класс указанной среды выполнения.

*TArg2*<br/>
Тип аргумента 2, который передается в класс указанной среды выполнения.

*TArg3*<br/>
Тип аргумента 3, который передается в класс указанной среды выполнения.

*TArg4*<br/>
Тип аргумента 4, который передается в класс указанной среды выполнения.

*TArg5*<br/>
Тип аргумента 5, который передается в класс указанной среды выполнения.

*TArg6*<br/>
Тип аргумента 6, передаваемое указанного класса среды выполнения.

*TArg7*<br/>
Тип аргумента 7, который передается в класс указанной среды выполнения.

*TArg8*<br/>
Тип аргумента 8, который передается в класс указанной среды выполнения.

*TArg9*<br/>
Тип аргумента 9, который передается в класс указанной среды выполнения.

*arg1*<br/>
Аргумент 1, который передается в класс указанной среды выполнения.

*Arg2*<br/>
Аргумент 2, который передается в класс указанной среды выполнения.

*arg3*<br/>
Аргумент 3, который передается в класс указанной среды выполнения.

*arg4*<br/>
Аргумент 4, который передается в класс указанной среды выполнения.

*arg5*<br/>
Аргумент 5, который передается в класс указанной среды выполнения.

*arg6*<br/>
Аргумент 6, передаваемый в класс указанной среды выполнения.

*arg7*<br/>
Аргумент 7, который передается в класс указанной среды выполнения.

*arg8*<br/>
Аргумент 8, который передается в класс указанной среды выполнения.

*arg9*<br/>
Аргумент 9, передаваемый в класс указанной среды выполнения.

## <a name="return-value"></a>Возвращаемое значение

Объект `ComPtr<T>` объекта, если успешно; в противном случае — значение **nullptr**.

## <a name="remarks"></a>Примечания

См. в разделе [как: непосредственно создания экземпляра компонентов WRL](../windows/how-to-instantiate-wrl-components-directly.md) в этой статье описаны различия между этой функцией и [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)и примеры.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)