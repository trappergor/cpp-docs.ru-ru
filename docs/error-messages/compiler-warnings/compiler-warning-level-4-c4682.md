---
title: "Предупреждение компилятора предупреждение (уровень 4) C4682 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4682
dev_langs:
- C++
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 718382c17fd0b108322a29f99c3b3a2d2c813d6c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4682"></a>Предупреждение компилятора (уровень 4) C4682
"параметр": не указан атрибут параметра направления, по умолчанию принимается [in]  
  
 Метод параметра в интерфейсе с атрибутами не имеет одного атрибута направления: [в](../../windows/in-cpp.md) или [out](../../windows/out-cpp.md). По умолчанию принимается атрибут in.  
  
 Это предупреждение отключено по умолчанию. В разделе [компилятора предупреждения выключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) для получения дополнительной информации.  
  
 Следующий пример приводит к возникновению предупреждения C4682:  
  
```  
// C4682.cpp  
// compile with: /W4  
#pragma warning(default : 4682)  
#include <windows.h>  
[module(name="MyModule")];  
  
[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]  
__interface IMyIface : IUnknown  
{  
   HRESULT f1(int i, int *pi); // C4682  
   // try the following line  
   // HRESULT f1([in] int i, [in] int *pi);  
};  
  
int main()  
{  
}  
```
