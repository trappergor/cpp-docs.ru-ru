---
title: _bstr_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
ms.openlocfilehash: 97f0100d8a34253f3a1375d34b887d3d31a77f43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350875"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =

**Блок, относящийся только к системам Microsoft**

Присваивает новое значение существующему объекту `_bstr_t`.

## <a name="syntax"></a>Синтаксис

```
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

#### <a name="parameters"></a>Параметры

*s1*<br/>
Объект `_bstr_t`, который требуется присвоить существующему объекту `_bstr_t`.

*s2*<br/>
Многобайтовая строка, которую требуется присвоить существующему объекту `_bstr_t`.

*S3*<br/>
Строка Юникода, которую требуется присвоить существующему объекту `_bstr_t`.

*var*<br/>
Объект `_variant_t`, который требуется присвоить существующему объекту `_bstr_t`.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="example"></a>Пример

См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример использования **оператор =**.

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)