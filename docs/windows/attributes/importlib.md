---
title: importlib (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: 29c7df8fbedbd107a9bb0b05466addc4672fc555
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041449"
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