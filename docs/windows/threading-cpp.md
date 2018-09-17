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
ms.openlocfilehash: 899c41a65a651f7464b11639d2106b3eaa51e21b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708660"
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

[Атрибуты COM](../windows/com-attributes.md)  
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  
[Поддержка многопоточности для устаревшего кода (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)  
[Нейтральный подразделения](/windows/desktop/cossdk/neutral-apartments)  