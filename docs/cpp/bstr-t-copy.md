---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 1fe8cfb5b644b3c7c34cf3325a91ebdf23a04946
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190330"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Блок, относящийся только к системам Microsoft**

Создает копию инкапсулированного объекта `BSTR`.

## <a name="syntax"></a>Синтаксис

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Параметры

*фкопи*<br/>
Если значение равно TRUE, **Copy** возвращает копию вложенного `BSTR`, в противном случае **Copy** возвращает фактическую BSTR.

## <a name="remarks"></a>Remarks

Возвращает копию инкапсулированного объекта `BSTR`, для которого выделена память.

## <a name="example"></a>Пример

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[_bstr_t Class](../cpp/bstr-t-class.md)
