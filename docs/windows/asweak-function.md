---
title: AsWeak - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: 0c3250b18422f64e71d8e8d7dac8dc5ab204145b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616740"
---
# <a name="asweak-function"></a>AsWeak - функция

Извлекает слабую ссылку на определенный экземпляр.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Указатель на тип параметра *p*.

*p*<br/>
Экземпляр типа.

*pWeak*<br/>
После завершения операции, указатель на слабую ссылку на параметр *p*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция выполнена успешно; в противном случае ошибка HRESULT, указывающее причину сбоя.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)