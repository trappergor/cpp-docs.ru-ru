---
title: UUID (атрибуты C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36b438662fb42cdeeb894906753a38168208f5ae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218823"
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

*uuid*  
128-разрядный, уникальный идентификатор.

## <a name="remarks"></a>Примечания

Если не содержит определение интерфейса или класса **uuid** атрибут C++, а затем компилятор Visual C++ выдает один. При указании **uuid**, необходимо указывать в кавычках.

Если вы не укажете **uuid**, то компилятор создаст один и тот же GUID для интерфейсов или классов с тем же именем в другой атрибут проектов на компьютере.

Uuidgen.exe и Guidgen.exe можно использовать для создания собственных уникальных идентификаторов. (Для запуска этих средств, нажмите кнопку **запустить** и нажмите кнопку **запуска** меню. Затем введите имя необходимые средства.)

При использовании в проекте, который также не используйте ATL, указав **uuid** атрибут же эффект достигается указанием [uuid](../cpp/uuid-cpp.md) **__declspec** модификатор. Для получения **uuid** класса, можно использовать [__uuidof](../cpp/uuidof-operator.md)

## <a name="example"></a>Пример

См. в разделе [bindable](../windows/bindable.md) пример для использовать **uuid**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**, **интерфейс**, **объединение**, **enum**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[uuid](/windows/desktop/Midl/uuid)  