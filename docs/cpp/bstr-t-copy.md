---
title: _bstr_t::Copy | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50f9a17c93849dec49c2c9a72825a5797d8c040c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068628"
---
# <a name="bstrtcopy"></a>_bstr_t::copy

**Блок, относящийся только к системам Microsoft**

Создает копию инкапсулированного объекта `BSTR`.

## <a name="syntax"></a>Синтаксис

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Параметры

*fCopy*<br/>
Если значение равно TRUE, **копирования** возвращает копию содержащегося `BSTR`, в противном случае **копирования** возвращает фактический объект BSTR.

## <a name="remarks"></a>Примечания

Возвращает копию инкапсулированного объекта `BSTR`, для которого выделена память.

## <a name="example"></a>Пример

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)