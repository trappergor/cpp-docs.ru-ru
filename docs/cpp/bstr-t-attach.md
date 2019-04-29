---
title: _bstr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::Attach
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
ms.openlocfilehash: 8601ebbea6a9ab837c07518b018e83e8c0df226d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385067"
---
# <a name="bstrtattach"></a>_bstr_t::Attach

**Блок, относящийся только к системам Microsoft**

Связывает упаковщик `_bstr_t` со строкой `BSTR`.

## <a name="syntax"></a>Синтаксис

```
void Attach(
   BSTR s
);
```

#### <a name="parameters"></a>Параметры

*s*<br/>
Ресурс `BSTR` для связывания с переменной `_bstr_t` или назначения ей.

## <a name="remarks"></a>Примечания

Если переменная `_bstr_t` была ранее присоединена к другому ресурсу `BSTR`, `_bstr_t` очистит ресурсы `BSTR`, если другие переменные `_bstr_t` не используют `BSTR`.

## <a name="example"></a>Пример

См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) в качестве примера использования **Attach**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)