---
title: _bstr_t::GetBSTR | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a62cd1c08409fb5915ebf42fa118c1e6124e29f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071865"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR

**Блок, относящийся только к системам Microsoft**

Указывает на начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.

## <a name="syntax"></a>Синтаксис

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>Возвращаемое значение

Начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.

## <a name="remarks"></a>Примечания

**GetBSTR** влияет на все `_bstr_t` объектов данной общей папки `BSTR`. Более одного `_bstr_t` могут совместно использовать `BSTR` при помощи конструктора копии и **оператор =**.

## <a name="example"></a>Пример

См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) в качестве примера использования **GetBSTR**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[_bstr_t Class](../cpp/bstr-t-class.md)