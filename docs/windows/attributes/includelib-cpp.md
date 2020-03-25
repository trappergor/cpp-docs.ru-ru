---
title: инклуделиб (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 4022a3f1f2d4ccaabe65c24065be8e1c846d604d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214853"
---
# <a name="includelib-c"></a>includelib (C++)

Вызывает включение IDL-или h-файла в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>Параметры

*Name. idl*<br/>
Имя IDL-файла, который должен быть включен в состав созданного idl-файла.

## <a name="remarks"></a>Remarks

Атрибут **инклуделиб** C++ вызывает включение IDL-или h-файла в созданный IDL-файл после инструкции `importlib`.

## <a name="example"></a>Пример

В cpp-файле показан следующий код:

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Да|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)
