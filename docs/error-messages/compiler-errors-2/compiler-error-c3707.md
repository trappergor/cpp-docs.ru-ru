---
title: "Ошибка компилятора C3707 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7167ea0df9bc0846de16be40d722c63bfea11c32
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3707"></a>Ошибка компилятора C3707
«функция»: метод disp-интерфейса должен иметь dispid  
  
 Если вы используете `dispinterface` метод, необходимо назначить `dispid`. Чтобы устранить эту ошибку, назначьте `dispid` для `dispinterface` метода, например, Раскомментировать `id` атрибута в методе в примере ниже. Дополнительные сведения см. в разделе атрибуты [disp-интерфейса](../../windows/dispinterface.md) и [идентификатор](../../windows/id.md).  
  
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
