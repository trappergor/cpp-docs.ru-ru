---
title: _bstr_t::GetAddress | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b3aa001270a3dc608fabf73fce28ce51eb9295e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031305"
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress

**Блок, относящийся только к системам Microsoft**

Освобождает любую существующую строку и возвращает адрес новой строки, которой была выделена память.

## <a name="syntax"></a>Синтаксис

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на строку `BSTR`, инкапсулированную объектом `_bstr_t`.

## <a name="remarks"></a>Примечания

**GetAddress** влияет на все `_bstr_t` объектов данной общей папки `BSTR`. Более одного `_bstr_t` могут совместно использовать `BSTR` при помощи конструктора копии и **оператор =**.

## <a name="example"></a>Пример

См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример с использованием **GetAddress**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)