---
title: Создание потоков (атрибут COM в C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: e08d25df07ad881c8843953d01d9074c815ddb85
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193072"
---
# <a name="threading-c"></a>threading (C++)

Указывает потоковую модель для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Параметры

*model*<br/>
Используемых Одна из следующих потоков моделей:

- `apartment`(потоковое разделение)

- `neutral`(.NET Framework компонентов без пользовательского интерфейса)

- `single`(простая организация потоков)

- `free`(свободная организация)

- `both`(потоковая подразделение и свободная организация)

Значение по умолчанию — `apartment`.

## <a name="remarks"></a>Примечания

Атрибут **Threading** C++ не отображается в созданном IDL-файле, но будет использоваться в реализации объекта COM.

В проектах ATL, если имеется также атрибут [coclass](coclass.md) , потоковая модель, заданная *моделью* , передается в качестве параметра шаблона в класс [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) , который вставляется `coclass` атрибутом.

Атрибут **потоковой обработки** также защищает доступ к [event_source](event-source.md).

## <a name="example"></a>Пример

Пример использования **потоков**см. в примере с [лицензией](licensed.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Поддержка многопоточности для устаревшего кода (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Нейтральные подразделения](/windows/win32/cossdk/neutral-apartments)
