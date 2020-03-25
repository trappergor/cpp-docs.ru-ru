---
title: library_block (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 405cc1cd5af7dcd689e833764f3da2fdc6d5f703
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214777"
---
# <a name="library_block"></a>library_block

Размещает конструкцию внутри блока библиотеки IDL.

## <a name="syntax"></a>Синтаксис

```cpp
[library_block]
```

## <a name="remarks"></a>Remarks

При помещении конструкции в блок библиотеки вы гарантируете, что она будет передаваться в библиотеку типов, независимо от того, есть ли на нее ссылка. По умолчанию в блок библиотеки помещаются только конструкции, измененные атрибутами [coclass](coclass.md), [DISP](dispinterface.md)и [idl_module](idl-module.md) .

## <a name="example"></a>Пример

В следующем коде пользовательский интерфейс помещается внутрь блока Library.

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
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)
