---
title: library_block (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 76e643cb45d8a87408015e6e0726e47d423147f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459930"
---
# <a name="libraryblock"></a>library_block

Помещает конструкцию внутри блока библиотеки IDL.

## <a name="syntax"></a>Синтаксис

```cpp
[library_block]
```

## <a name="remarks"></a>Примечания

При размещении конструкции внутри блока библиотеки, убедитесь, что он будет передан в библиотеку типов, независимо от того, является ли он указывается. По умолчанию, единственными конструкциями модификаторами [coclass](coclass.md), [disp-интерфейс](dispinterface.md), и [idl_module](idl-module.md) атрибуты помещаются в блок library.

## <a name="example"></a>Пример

В следующем коде пользовательский интерфейс помещается в блок library.

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)