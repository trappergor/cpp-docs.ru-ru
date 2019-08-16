---
title: uuid (атрибуты C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: d644f59ac92bf4e39f191c291dd4fef626411c3d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514947"
---
# <a name="uuid-c-attributes"></a>uuid (атрибуты C++)

Задает уникальный идентификатор класса или интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[ uuid(
   "uuid"
) ]
```

### <a name="parameters"></a>Параметры

*uuid*<br/>
128-разрядный уникальный идентификатор.

## <a name="remarks"></a>Примечания

Если в определении интерфейса или класса не задан атрибут **UUID** C++ , то компилятор Майкрософт C++ предоставит его. При указании **UUID**необходимо включить кавычки.

Если не указать **UUID**, компилятор создаст тот же идентификатор GUID для интерфейсов или классов с тем же именем в разных проектах атрибутов на компьютере.

Вы можете использовать uuidgen. exe или guidgen. exe для создания собственных уникальных идентификаторов. (Чтобы запустить любой из этих средств, нажмите кнопку **Пуск** и выберите пункт **выполнить** в меню. Затем введите имя требуемого инструмента.)

При использовании в проекте, который не использует ATL, указание атрибута **UUID** аналогично указанию модификатора [UUID](../../cpp/uuid-cpp.md) **__declspec** . Чтобы получить **UUID** класса, можно использовать [__uuidof](../../cpp/uuidof-operator.md)

## <a name="example"></a>Пример

Пример использования **UUID**см. в примере с [возможностью привязки](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **Структура**, **интерфейс**, **объединение**, перечисление|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/win32/Midl/uuid)