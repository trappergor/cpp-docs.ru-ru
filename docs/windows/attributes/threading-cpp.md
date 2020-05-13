---
title: Потоковая модельC++ (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: b249eaf61266ed9964e44f6f0ad1c2f12a1b1067
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214504"
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

- `apartment` (потоковое разделение)

- `neutral` (.NET Framework компонентов без пользовательского интерфейса)

- `single` (простые потоки)

- `free` (свободная организация)

- `both` (потоковая подразделение и свободная организация)

Значение по умолчанию — `apartment`.

## <a name="remarks"></a>Remarks

C++ Атрибут **потоковой обработки** не отображается в созданном IDL-файле, но будет использоваться в реализации объекта COM.

В проектах ATL, если атрибут [coclass](coclass.md) также имеется, потоковая модель, заданная *моделью* , передается в качестве параметра шаблона классу [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) , вставленному атрибутом `coclass`.

Атрибут **потоковой обработки** также защищает доступ к [event_source](event-source.md).

## <a name="example"></a>Пример

Пример использования **потоков**см. в примере с [лицензией](licensed.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Поддержка многопоточности для устаревшего кода (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Нейтральные подразделения](/windows/win32/cossdk/neutral-apartments)
