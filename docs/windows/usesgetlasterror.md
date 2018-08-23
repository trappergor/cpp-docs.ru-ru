---
title: usesgetlasterror | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7921ff48adf2f987844557f9af3be5adcd6736de
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602766"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Вызывающий объект о том, есть ли ошибки при вызове этой функции, затем вызывающий объект затем можно вызвать `GetLastError` для получения кода ошибки.

## <a name="syntax"></a>Синтаксис

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Примечания

**Usesgetlasterror** атрибут C++ имеет ту же функциональность, что [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [idl_module](../windows/idl-module.md) примере образец демонстрирует использование **usesgetlasterror**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**модуль** атрибут|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  