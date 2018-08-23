---
title: запись | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f9bc6a88ee7dca0bcd4ad2f87fd3aa4c318d8b9d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604769"
---
# <a name="entry"></a>entry

Указывает экспортированной функции или константы в модуле, определяя точки входа в библиотеку DLL.

## <a name="syntax"></a>Синтаксис

```cpp
[ entry(
   id
) ]
```

### <a name="parameters"></a>Параметры

*id*  
Идентификатор точки входа.

## <a name="remarks"></a>Примечания

**Запись** атрибут C++ имеет ту же функциональность, что [запись](http://msdn.microsoft.com/library/windows/desktop/aa366815) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [idl_module](../windows/idl-module.md) для пример использования **запись**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Атрибут `idl_module`|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  