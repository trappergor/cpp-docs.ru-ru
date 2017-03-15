---
title: "idl_module | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.idl_module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_module attribute"
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# idl_module
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет точку входа в DLL\-файл.  
  
## Синтаксис  
  
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
  
#### Параметры  
 **Имя**  
 Определяемое пользователем имя блока кода, который отображается в idl\-файл.  
  
 **dllname** \(необязательно\)  
 DLL\-файл, содержащий экспорт.  
  
 `uuid` \(необязательный параметр\)  
 Уникальный идентификатор.  
  
 **Сттрока справки** \(необязательно\)  
 Символьная строка, используемая для описания библиотеку типов.  
  
 **helpstringcontext** \(необязательно\)  
 Идентификатор раздела в файле справки .hlp или .chm.  
  
 **Контекст справки** \(необязательно\)  
 Идентификатор Справки для данной библиотеки типов.  
  
 **скрытый** \(необязательно\)  
 Параметр, который предотвращает из библиотеки.  Эти [скрытый](http://msdn.microsoft.com/library/windows/desktop/aa366861) Атрибут MIDL дополнительные сведения.  
  
 ***restricted***  \(необязательно\)  
 Члены библиотек не могут произвольно вызова.  Эти restricted Атрибут MIDL дополнительные сведения.  
  
 *объявление функции*  
 Функция, которую вы определите.  
  
## Заметки  
 `idl_module` Атрибут C\+\+ позволяет указать точку входа в DLL\-файл, которая позволяет ввозу из dll\-файла.  
  
 **idl\_module** атрибут имеет возможности, аналогичные  [Модуль](http://msdn.microsoft.com/library/windows/desktop/aa367099) атрибут MIDL.  
  
 Можно экспортировать что\-либо из com\-объекта, можно экспортировать из dll\-файла, поместив точку входа DLL в блоке библиотеки файла idl.  
  
 Использование сусла `idl_module` в шаге 2.  Во\-первых, необходимо указать пару месяца или DLL.  Затем при использовании `idl_module` чтобы задать точку входа, укажите имя и любые дополнительные атрибуты.  
  
## Пример  
 В следующем примере кода демонстрируется применение `idl_module` атрибут:  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Любой|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [entry](../windows/entry.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)