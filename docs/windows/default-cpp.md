---
title: "default (C++) | Microsoft Docs"
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
  - "vc-attr.default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default - атрибут"
  - "атрибуты [C#], атрибут default"
  - "атрибут default"
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# default (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что настраиваемый или disp\-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.  
  
## Синтаксис  
  
```  
  
[ default(  
interface1  
,  
   interface2  
) ]  
  
```  
  
#### Параметры  
 *interface1*  
 Интерфейс по умолчанию, который будет доступен в средах разработки сценариев, где создаются объекты на основе класса, определенного с помощью атрибута **default**.  
  
 Если исходный интерфейс по умолчанию не указан, в качестве интерфейса по умолчанию используется первое вхождение неисходного интерфейса.  
  
 *interface2*\(необязательно\)  
 Исходный интерфейс по умолчанию. Этот интерфейс также необходимо указать с помощью атрибута [source](../Topic/source%20\(C++\).md).  
  
 Если исходный интерфейс по умолчанию не указан, в качестве интерфейса по умолчанию используется первый исходный интерфейс.  
  
## Заметки  
 Атрибут **default** языка C\+\+ имеет ту же функциональность, что и атрибут [default](http://msdn.microsoft.com/library/windows/desktop/aa366787) языка MIDL. Атрибут **default** также используется вместе с атрибутом [case](../windows/case-cpp.md).  
  
## Пример  
 В приведенном далее коде показано использование атрибута **default** в определении кокласса для указания **ICustomDispatch** в качестве интерфейса программирования по умолчанию.  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 Атрибут [source](../Topic/source%20\(C++\).md) также содержит пример использования атрибута **default**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**, `struct`, элемент данных|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**кокласс** \(при применении к **классу** или `struct`\)|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)