---
title: idl_module | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_module
dev_langs:
- C++
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0539275a09a64e31a9ecad17cab899368701e353
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412220"
---
# <a name="idlmodule"></a>idl_module

Указывает точку входа в DLL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ idl_module (
   name=module_name,
   dllname=dll,
   uuid="uuid",
   helpstring="help text",
   helpstringcontext=helpcontextID,
   helpcontext=helpcontext,
   hidden,
   restricted
) ]
function declaration
```

### <a name="parameters"></a>Параметры

*name*<br/>
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
(Необязательно) Параметр, который запрещает отображение библиотеки. См. в разделе [скрытые](/windows/desktop/Midl/hidden) описании атрибута MIDL Дополнительные сведения.

*restricted*<br/>
(Необязательно) Элементы библиотеки нельзя вызывать произвольным образом. См. в разделе [ограниченных](/windows/desktop/Midl/restricted) описании атрибута MIDL Дополнительные сведения.

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

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Изолированные атрибуты](../windows/stand-alone-attributes.md)<br/>
[entry](../windows/entry.md)  