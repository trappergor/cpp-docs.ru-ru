---
title: Ошибка компилятора C3707 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7268f584d9f269b4f2f15b837379ec12ab0185d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273729"
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