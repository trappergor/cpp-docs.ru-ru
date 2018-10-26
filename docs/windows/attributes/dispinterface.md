---
title: disp-интерфейс (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea3ece20ac6df0fab00f1e21d27c41ae6e115517
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065906"
---
# <a name="dispinterface"></a>dispinterface

Помещает интерфейс в IDL-файл в качестве интерфейса диспетчеризации.

## <a name="syntax"></a>Синтаксис

```cpp
[dispinterface]
```

## <a name="remarks"></a>Примечания

Если интерфейсу предшествует атрибут **dispinterface** языка C++, это вызывает помещение интерфейса в блок library созданного IDL-файла.

Если не указать базовый класс, интерфейс диспетчеризации будет производным от `IDispatch`. Необходимо указать [идентификатор](id.md) для членов интерфейса диспетчеризации.

Пример использования [dispinterface](/windows/desktop/Midl/dispinterface) в документации MIDL:

```cpp
dispinterface helloPro
   { interface hello; };
```

не является допустимым для атрибута **dispinterface** .

## <a name="example"></a>Пример

Просмотрите пример с [bindable](bindable.md) , чтобы увидеть, как можно использовать **dispinterface**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Список атрибутов по использованию](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[custom](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)