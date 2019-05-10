---
title: uuid (атрибуты C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: eae79f9a4d0af6375834c0792c4004f52a16e07e
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448928"
---
# <a name="uuid-c-attributes"></a>uuid (атрибуты C++)

Указывает уникальный идентификатор для класса или интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[ uuid(
   "uuid"
) ]
```

### <a name="parameters"></a>Параметры

*uuid*<br/>
128-разрядный, уникальный идентификатор.

## <a name="remarks"></a>Примечания

Если не содержит определение интерфейса или класса **uuid** C++ атрибут, а затем Microsoft C++ компилятор выдает один. При указании **uuid**, необходимо указывать в кавычках.

Если вы не укажете **uuid**, то компилятор создаст один и тот же GUID для интерфейсов или классов с тем же именем в другой атрибут проектов на компьютере.

Uuidgen.exe и Guidgen.exe можно использовать для создания собственных уникальных идентификаторов. (Для запуска этих средств, нажмите кнопку **запустить** и нажмите кнопку **запуска** меню. Затем введите имя необходимые средства.)

При использовании в проекте, который также не используйте ATL, указав **uuid** атрибут же эффект достигается указанием [uuid](../../cpp/uuid-cpp.md) **__declspec** модификатор. Для получения **uuid** класса, можно использовать [__uuidof](../../cpp/uuidof-operator.md)

## <a name="example"></a>Пример

См. в разделе [bindable](bindable.md) пример для использовать **uuid**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**, **интерфейс**, **объединение**, **enum**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/desktop/Midl/uuid)