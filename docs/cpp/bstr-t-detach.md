---
title: _bstr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: cc8284bd-f68b-4fff-b2e6-ce8354dabf8b
ms.openlocfilehash: 51561c6f7cf5ba49c86f818d925db548438b2981
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492196"
---
# <a name="bstrtdetach"></a>_bstr_t::Detach

**Блок, относящийся только к системам Microsoft**

Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее (`BSTR`) от этого объекта (`_bstr_t`).

## <a name="syntax"></a>Синтаксис

```
BSTR Detach( ) throw;
```

## <a name="return-value"></a>Возвращаемое значение

`BSTR` в оболочке `_bstr_t`.

## <a name="example"></a>Пример

См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример с использованием **отсоединения**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)