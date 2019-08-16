---
title: Потоковая модельC++ (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: db2940ec3536ae8ea29ba40db84ea869ecb3d0ac
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513928"
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

Значение по умолчанию — `apartment`.

## <a name="remarks"></a>Примечания

Атрибут потоковой обработки не отображается в созданном IDL-файле, но будет использоваться в реализации объекта COM. C++

В проектах ATL, если имеется также атрибут [coclass](coclass.md) , потоковая модель, заданная *моделью* , передается в качестве параметра шаблона в `coclass` класс [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) , который вставляется атрибутом.

Атрибут **потоковой обработки** также защищает доступ к [event_source](event-source.md).

## <a name="example"></a>Пример

Пример использования **потоков**см. в примере с [лицензией](licensed.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **Структура**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Поддержка многопоточности для устаревшего кода (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Нейтральные подразделения](/windows/win32/cossdk/neutral-apartments)