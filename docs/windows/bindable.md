---
title: "bindable | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.bindable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bindable attribute"
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bindable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что свойство поддерживает привязку данных.  
  
## Синтаксис  
  
```  
  
[bindable]  
  
```  
  
## Заметки  
 **bindable** Атрибут C\+\+ имеет ту же функциональность, что и  [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738) атрибут MIDL.  Можно использовать его для свойств, определенных с [propget](../windows/propget.md)"  [propput](../windows/propput.md)или  [propputref](../windows/propputref.md) атрибуты, либо можно вручную определить связываемая метод.  
  
 В следующих примерах показано использование MFC bindable.  
  
-   [Примеры элементов управления: MFC\-Основанные управления ActiveX](http://msdn.microsoft.com/ru-ru/a44adf86-0ba0-4504-bedb-512b6cba2e63)  
  
-   [Образец CIRC: элемент управления ActiveX](http://msdn.microsoft.com/ru-ru/9ba34d04-280e-49f4-90ae-41a6be44c95b)  
  
-   [Образец TESTHELP: элемент управления ActiveX с подсказками и справкой](http://msdn.microsoft.com/ru-ru/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)  
  
## Пример  
 Следующий код показывает, как можно использовать bindable свойства:  
  
```  
// cpp_attr_ref_bindable.cpp  
// compile with: /LD  
#include <windows.h>  
[  
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),  
   dispinterface,  
   helpstring("property demo Interface")  
]  
__interface IPropDemo : IDispatch {  
  
   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);  
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);  
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);  
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);     
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();  
};  
  
[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Метод интерфейса|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [defaultbind](../windows/defaultbind.md)   
 [displaybind](../windows/displaybind.md)   
 [immediatebind](../windows/immediatebind.md)   
 [requestedit](../windows/requestedit.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)