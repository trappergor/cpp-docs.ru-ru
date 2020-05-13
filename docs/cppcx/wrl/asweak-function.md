---
title: Функция AsWeak
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: d11f55d57f4053fd6d46b727a8ed91b340d1764b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214179"
---
# <a name="asweak-function"></a>Функция AsWeak

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

*пвеак*<br/>
По завершении этой операции указатель на слабую ссылку на параметр *p*.

## <a name="return-value"></a>Возвращаемое значение

S_OK, если эта операция выполнена успешно; в противном случае возвращается ошибка HRESULT, указывающая причину сбоя.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
