---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c121ad99dfbe0021a263f324ccdb9a95441bba33
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740463"
---
# <a name="uuid-c"></a>uuid (C++)

**Блок, относящийся только к системам Microsoft**

Компилятор присоединяет идентификатор GUID к классу или структуре, объявленным или определенным (только для полных определений COM-объектов) с атрибутом **UUID** .

## <a name="syntax"></a>Синтаксис

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Примечания

Атрибут **UUID** принимает в качестве аргумента строку. Эта строка присваивает идентификатор GUID в стандартном формате реестра с разделителями **{}** или без них. Например:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Этот атрибут можно применить при повторном объявлении. Это позволяет заголовкам систем предоставлять определения интерфейсов, таких как `IUnknown`, и повторное объявление в каком-либо другом заголовке ( \<например, COMDEF. h >) для предоставления идентификатора GUID.

Ключевое слово [__uuidof](../cpp/uuidof-operator.md) можно применить для получения постоянного GUID, присоединенного к определяемому пользователем типу.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)