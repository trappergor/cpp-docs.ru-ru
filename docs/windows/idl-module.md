---
title: idl_module | Документы Microsoft
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
ms.openlocfilehash: 11547a3fb1bd46a1e2edb8ce9dd0a6547464f796
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882528"
---
# <a name="idlmodule"></a>idl_module
Указывает точку входа в DLL-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
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
  
#### <a name="parameters"></a>Параметры  
 **name**  
 Определяемое пользователем имя для блока кода, который будет отображаться в IDL-файл.  
  
 **имя DLL-библиотеки** (необязательно)  
 DLL-файл, содержащий экспорта.  
  
 `uuid` (необязательно)  
 Уникальный идентификатор.  
  
 **HelpString** (необязательно)  
 Строка символов, используемый для описания библиотеки типов.  
  
 **helpstringcontext** (необязательно)  
 Идентификатор раздела справки в .hlp или CHM-файле.  
  
 **helpcontext** (необязательно)  
 Идентификатор справки для этой библиотеки типов.  
  
 **hidden** (необязательно)  
 Параметр, который препятствует отображению библиотеки. Дополнительные сведения см. в описании атрибута MIDL [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) .  
  
 ***ограниченные*** (необязательно)  
 Члены библиотеки не может вызываться произвольным образом. Дополнительные сведения см. в описании атрибута MIDL [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) .  
  
 *объявление функции*  
 Функция, которая будет определена.  
  
## <a name="remarks"></a>Примечания  
 `idl_module` Языка c++ позволяет указать точку входа в DLL-файл, который можно импортировать из DLL-файла.  
  
 **Idl_module** атрибут имеет функциональность, аналогичную [модуль](http://msdn.microsoft.com/library/windows/desktop/aa367099) языка MIDL.  
  
 Никаких действий можно экспортировать из COM-объект, который можно экспортировать из DLL-файла, поместив точки входа библиотеки DLL в блок library IDL-файл.  
  
 Ваш необходимо использовать `idl_module` в два этапа. Во-первых необходимо определить пары имя/DLL. Затем, при использовании `idl_module` для указания точки входа, укажите имя и дополнительные атрибуты.  
  
## <a name="example"></a>Пример  
 Следующий код показывает, как использовать `idl_module` атрибута:  
  
```  
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
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
 [entry](../windows/entry.md)   
