---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: cea3404e0732cb0e16b3fa9199ce95e3dfcc23f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386152"
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