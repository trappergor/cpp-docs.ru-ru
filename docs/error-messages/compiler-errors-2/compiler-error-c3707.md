---
title: "Ошибка компилятора C3707 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3707"
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": метод disp\-интерфейса должен иметь dispid  
  
 При использовании метода `dispinterface` ему необходимо присвоить `dispid`.  Чтобы устранить эту ошибку, присвойте методу `dispinterface` `dispid`. Например, в следующем примере для этого удаляется метка комментария с атрибута `id` для метода.  Дополнительные сведения см. в описании атрибутов [dispinterface](../../windows/dispinterface.md) и [id](../../windows/id.md).  
  
 Следующий пример приводит к возникновению ошибки C3707:  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```