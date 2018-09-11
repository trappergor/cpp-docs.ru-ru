---
title: Функция AsWeak | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dea10165e920c6b0bbd3856fc04e9ec9661e60c4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571338"
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

*T*  
Указатель на тип параметра *p*.

*p*  
Экземпляр типа.

*pWeak*  
После завершения операции, указатель на слабую ссылку на параметр *p*.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция выполнена успешно; в противном случае ошибка HRESULT, указывающее причину сбоя.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)