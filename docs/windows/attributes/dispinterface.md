---
title: ДиспетчерскийC++ интерфейс (атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: 6360c5e97eae19d7b2d74b3b43d4feae07d4b091
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501617"
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

Пример использования [dispinterface](/windows/win32/Midl/dispinterface) в документации MIDL:

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
|**Относится к**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
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