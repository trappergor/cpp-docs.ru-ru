---
title: idl_module (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 80e4909a61b5b53ecde19471f2c838dd4c425874
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034982"
---
# <a name="idlmodule"></a>idl_module

Указывает точку входа в DLL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>Параметры

*имя*<br/>
Определяемое пользователем имя для блока кода, который будет отображаться в IDL-файла.

*dllname*<br/>
(Необязательно) DLL-файл, содержащий экспорта.

*uuid*<br/>
(Необязательно) Уникальный идентификатор.

*helpstring*<br/>
(Необязательно) Строка символов, используемый для описания библиотеки типов.

*helpstringcontext*<br/>
(Необязательно) Идентификатор раздела справки в файл с расширением .hlp или .chm.

*helpcontext*<br/>
(Необязательно) Идентификатор справки для этой библиотеки типов.

*hidden*<br/>
(Необязательно) Параметр, который запрещает отображение библиотеки. Дополнительные сведения см. в описании атрибута MIDL [hidden](/windows/desktop/Midl/hidden) .

*restricted*<br/>
(Необязательно) Элементы библиотеки нельзя вызывать произвольным образом. Дополнительные сведения см. в описании атрибута MIDL [restricted](/windows/desktop/Midl/restricted) .

*объявление функции*<br/>
Функция, которую вы создадите.

## <a name="remarks"></a>Примечания

**Idl_module** C++ атрибут позволяет указать точку входа в DLL-файл, который можно импортировать из файла DLL.

**Idl_module** атрибут имеет функциональность, аналогичную [модуль](/windows/desktop/Midl/module) описании атрибута MIDL.

Никаких действий можно экспортировать из COM-объект, который можно экспортировать из DLL-файл, поместив точки входа библиотеки DLL в блок library IDL-файле.

Ваш необходимо использовать **idl_module** в два этапа. Во-первых необходимо определить пару имя/DLL. Затем, при использовании **idl_module** для указания точки входа, укажите имя и дополнительные атрибуты.

## <a name="example"></a>Пример

Ниже показано, как использовать **idl_module** атрибут:

```cpp
// cpp_attr_ref_idl_module.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];
[idl_module(name="MyLib"), entry(4), usesgetlasterror]
void FuncName(int i);
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

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[entry](entry.md)