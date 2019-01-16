---
title: AsWeak - функция
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: 1332aa140a8298590ad83158e0ec1b75035c4e92
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337695"
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

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)