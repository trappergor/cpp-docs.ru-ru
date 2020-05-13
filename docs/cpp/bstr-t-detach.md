---
title: _bstr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: cc8284bd-f68b-4fff-b2e6-ce8354dabf8b
ms.openlocfilehash: e56ad29ae9e7fdcf7e8d354bda570364c7be8901
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181269"
---
# <a name="_bstr_tdetach"></a>_bstr_t::Detach

**Блок, относящийся только к системам Microsoft**

Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее (`BSTR`) от этого объекта (`_bstr_t`).

## <a name="syntax"></a>Синтаксис

```
BSTR Detach( ) throw;
```

## <a name="return-value"></a>Возвращаемое значение

`BSTR` в оболочке `_bstr_t`.

## <a name="example"></a>Пример

См. раздел [_bstr_t:: Assign](../cpp/bstr-t-assign.md) для примера с помощью **отсоединения**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_bstr_t Class](../cpp/bstr-t-class.md)
