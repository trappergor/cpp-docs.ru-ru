---
title: RaiseException - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: 08305c5d59d7e272aac87ad9aa183c8e82588632
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029963"
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

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)