---
title: "registration_script | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.registration_script"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registration_script attribute"
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# registration_script
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполняет указанный пользовательский скрипт регистрации.  
  
## Синтаксис  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### Параметры  
 *script*  
 Полный путь к пользовательскому файлу скрипта регистрации \(.rgs\).  Значение  **нет**как  `script = "none"`указывает, что coclass не имеют требования к регистрации.  
  
## Заметки  
 **registration\_script** Атрибут C\+\+ выполняет пользовательский скрипт регистрации указанного by  **скрипт**.  Если данный атрибут не определен, то стандартный файл, содержащий сведения .rgs \(\) используется для регистрации компонента.  Дополнительные сведения о файлах .rgs см. в разделе [Компонент реестра библиотеки ATL \(регистраторша\)](../atl/atl-registry-component-registrar.md).  
  
 Этот атрибут необходим [CoClass](../windows/coclass.md)"  [идентификатор progid](../Topic/progid.md)или  [vi\_progid](../windows/vi-progid.md) атрибут \(или другой атрибут, подразумевается одно из них\) также были применены к одному элементу.  
  
## Пример  
 Следующий код определяет, что компонент имеет скрипт реестра cpp\_attr\_ref\_registration\_script.rgs.  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|Одно или несколько из следующих значений: **CoClass**"  **идентификатор progid**или  **vi\_progid**.|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)