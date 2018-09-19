---
title: _bstr_t::operator = | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35778fe3bdf75738f67b280cbbe4c8ceeb498634
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017005"
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