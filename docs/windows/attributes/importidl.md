---
title: importidl (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 9db62d4f2a36b8cc0592c924b113077a758915c0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029918"
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
[импорт](import.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)