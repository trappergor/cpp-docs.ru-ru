---
title: back_inserter - функция
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: 82df6b06389fa9f1c3ab83fa7b1da3bab092c68d
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750745"
---
# <a name="backinserter-function"></a>back_inserter - функция

Возвращает итератор, используемый для вставки элементов в конце указанной коллекции.

## <a name="syntax"></a>Синтаксис

```

template <typename T>
Platform::BackInsertIterator<T>
    back_inserter(IVector<T>^ v);

template<typename T>
Platform::BackInsertIterator<T>
   back_inserter(IObservableVector<T>^ v);
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Параметр типа шаблона.

*v*<br/>
Указатель интерфейса, предоставляющий доступ к базовой коллекции.

### <a name="return-value"></a>Возвращаемое значение

Итератор.

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Windows::Foundation:: Collections

## <a name="see-also"></a>См. также

[Пространство имен Windows::Foundation:: Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)
