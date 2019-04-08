---
title: Функция MakeAndInitialize
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAndInitialize
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
ms.openlocfilehash: 14ae5117194748748ceecf97ac83fc8813bba2d3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037488"
---
# <a name="makeandinitialize-function"></a>Функция MakeAndInitialize

Инициализирует указанный класс среды выполнения Windows. Используйте эту функцию, чтобы создать экземпляр компонента, который определен в том же модуле.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename T,
    typename I,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9>
HRESULT MakeAndInitialize(
    _Outptr_result_nullonfailure_ I** ppvObject,
    TArg1 &&arg1,
    TArg2 &&arg2,
    TArg3 &&arg3,
    TArg4 &&arg4,
    TArg5 &&arg5,
    TArg6 &&arg6,
    TArg7 &&arg7,
    TArg8 &&arg8,
    TArg9 &&arg9) throw()
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

Значение HRESULT.

## <a name="remarks"></a>Примечания

См. практическое руководство по [ Создания экземпляра компонентов WRL непосредственно](how-to-instantiate-wrl-components-directly.md) в этой статье описаны различия между этой функцией и [Microsoft::wrl:: make](make-function.md)и примеры.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)