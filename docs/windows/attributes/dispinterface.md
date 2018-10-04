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
ms.openlocfilehash: 3b02244e0576f99cc0a6940f2ee4a13511cfbe6f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791104"
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

Пример использования [disp-интерфейс](/windows/desktop/Midl/dispinterface) в документации MIDL:

```cpp
dispinterface helloPro
   { interface hello; };
```

не является допустимым для атрибута **dispinterface** .

## <a name="example"></a>Пример

См. в примере [bindable](bindable.md) пример демонстрирует использование **disp-интерфейс**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Список атрибутов по использованию](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[Custom](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)  