---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: 09e40d38382bea0f902fda03d15d24e0cf1a627d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187808"
---
# <a name="uuid-c"></a>uuid (C++)

**Блок, относящийся только к системам Microsoft**

Компилятор присоединяет идентификатор GUID к классу или структуре, объявленным или определенным (только для полных определений COM-объектов) с атрибутом **UUID** .

## <a name="syntax"></a>Синтаксис

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Remarks

Атрибут **UUID** принимает в качестве аргумента строку. Эта строка присваивает идентификатор GUID в стандартном формате реестра с разделителями **{}** или без них. Пример:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Этот атрибут можно применить при повторном объявлении. Это позволяет заголовкам систем предоставлять определения интерфейсов, например `IUnknown`, и повторное объявление в каком-либо другом заголовке (например, \<comdef. h >) для предоставления идентификатора GUID.

Ключевое слово [__uuidof](../cpp/uuidof-operator.md) можно применить для получения постоянного GUID, присоединенного к определяемому пользователем типу.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
