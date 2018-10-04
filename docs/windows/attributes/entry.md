---
title: запись (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.entry
dev_langs:
- C++
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 95eb37898d4934740e1520df758ed33d3dd4c79a
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791247"
---
# <a name="entry"></a>entry

Указывает экспортированной функции или константы в модуле, определяя точки входа в библиотеку DLL.

## <a name="syntax"></a>Синтаксис

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Параметры

*id*<br/>
Идентификатор точки входа.

## <a name="remarks"></a>Примечания

**Запись** атрибут C++ имеет ту же функциональность, что [запись](/windows/desktop/Midl/entry) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [idl_module](idl-module.md) для пример использования **запись**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Атрибут `idl_module`|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)  