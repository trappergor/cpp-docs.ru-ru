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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3c61c23c093106267b4854109a8cfeb699bda78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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