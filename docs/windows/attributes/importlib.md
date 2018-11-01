---
title: importlib (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: d0bedb4bac91aa1a5aa72c8334db07aea0f04a97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649882"
---
# <a name="importlib"></a>importlib

Делает типы, которые уже были скомпилированы в другую библиотеку типов, доступными для создаваемой библиотеки типов.

## <a name="syntax"></a>Синтаксис

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>Параметры

*tlb_file*<br/>
Заключенное в кавычки имя TLB-файла, который необходимо импортировать в библиотеку типов текущего проекта.

## <a name="remarks"></a>Примечания

**Importlib** C++ атрибут приводит к `importlib` инструкцию, чтобы поместить в блок library созданного IDL-файла. **Importlib** атрибут имеет ту же функциональность, что [importlib](/windows/desktop/Midl/importlib) описании атрибута MIDL.

## <a name="example"></a>Пример

Ниже показан пример использования **importlib**:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
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
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)