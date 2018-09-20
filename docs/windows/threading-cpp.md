---
title: Работа с потоками (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ab2699781526ee12784f7c048cd9a833526fd30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415006"
---
# <a name="threading-c"></a>threading (C++)

Указывает потоковую модель для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ threading(
   model=enumeration
) ]
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

В проектах ATL Если [coclass](../windows/coclass.md) присутствует также атрибут, потоковой модели, указанный *модели* передается как параметр-шаблон [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) класса , вставленные `coclass` атрибута.

**Threading** атрибут также защищает доступ к [event_source](../windows/event-source.md).

## <a name="example"></a>Пример

См. в разделе [Лицензированные](../windows/licensed.md) пример для использовать **threading**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**coclass**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты COM](../windows/com-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](../windows/class-attributes.md)<br/>
[Поддержка многопоточности для устаревшего кода (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[Нейтральный подразделения](/windows/desktop/cossdk/neutral-apartments)  