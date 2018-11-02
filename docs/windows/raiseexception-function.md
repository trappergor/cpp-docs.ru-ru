---
title: RaiseException - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: af0b35e1014f79c7907711b95200c241d31b6117
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594757"
---
# <a name="raiseexception-function"></a>RaiseException - функция

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>Параметры

*hr*<br/>
Код исключения объекта исключения; то есть значение HRESULT неудачной операции.

*dwExceptionFlags*<br/>
Флаг, указывающий, допускающее исключения (значение флага равно нулю) или noncontinuable исключение (флаг значение отлично от нуля). По умолчанию исключение делающего продолжение невозможным.

## <a name="remarks"></a>Примечания

Вызывает исключение в вызывающем потоке.

Дополнительные сведения см. в разделе Windows `RaiseException` функции.

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)