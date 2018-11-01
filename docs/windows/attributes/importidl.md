---
title: importidl (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 8d0d891f74da8df2351b0a861fb7501e72f5e2de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587178"
---
# <a name="importidl"></a>importidl

Вставляет указанный IDL-файла в созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>Параметры

*idl_file*<br/>
Определяет имя IDL-файла, которые необходимо объединить с IDL-файла, создаваемого для вашего приложения.

## <a name="remarks"></a>Примечания

**Importidl** атрибут C++ помещает разделе за пределами блока библиотеки (в *idl_file*) в вашей программе созданного IDL-файла и в разделе библиотеки (в *idl_file*) в библиотеку раздел для вашей программы создается IDL-файла.

Вы можете использовать **importidl**, например, если вы хотите использовать с вашей созданного IDL-файла вручную IDL-файл.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)