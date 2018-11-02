---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: 4d51539d2afbb2fbcc860b6c4d821df119aca418
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601465"
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