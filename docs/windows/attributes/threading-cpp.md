---
title: Работа с потоками (C++ COM атрибут)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.threading
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
ms.openlocfilehash: cdebf06a62ebbd1d8648b9777fe200bc7a373261
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407241"
---
# <a name="threading-c"></a>threading (C++)

Указывает потоковую модель для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>Параметры

*model*<br/>
(Необязательно) Один из следующих моделей потоков:

- `apartment` (потоковое)

- `neutral` (Компоненты .NET framework без интерфейса пользователя)

- `single` (простой threading)

- `free` (свободным созданием потоков)

- `both` (подразделения и свободной потоковой модели)

Значение по умолчанию — `apartment`.

## <a name="remarks"></a>Примечания

**Threading** C++: атрибут не отображается в созданного IDL-файла, но будет использоваться в реализации COM-объекта.

В проектах ATL Если [coclass](coclass.md) присутствует также атрибут, потоковой модели, указанный *модели* передается как параметр-шаблон [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) класса , вставленные `coclass` атрибута.

**Threading** атрибут также защищает доступ к [event_source](event-source.md).

## <a name="example"></a>Пример

См. в разделе [Лицензированные](licensed.md) пример для использовать **threading**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Поддержка многопоточности для устаревшего кода (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Нейтральный подразделения](/windows/desktop/cossdk/neutral-apartments)