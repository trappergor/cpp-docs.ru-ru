---
title: "Предупреждение компилятора C4368 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6fd66d8fb6d30a960c659345910242ec5a1a2e11
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4368"></a>Предупреждение компилятора C4368
не удается определить «член» в качестве члена управляемого «тип»: смешанные типы не поддерживаются.  
  
 Элемент данных в собственном формате нельзя внедрять в тип CLR.  
  
 Однако, можно объявить указатель на неуправляемый тип и управления его жизненным циклом в конструктор и деструктор и метода завершения управляемого класса. Дополнительные сведения см. [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Это предупреждение всегда выдается как ошибка. Используйте [предупреждение](../../preprocessor/warning.md) pragma отключение C4368.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4368.  
  
```  
// C4368.cpp  
// compile with: /clr /c  
struct N {};  
ref struct O {};  
ref struct R {  
    R() : m_p( new N ) {}  
    ~R() { delete m_p; }  
  
   property N prop;   // C4368  
   int i[10];   // C4368  
  
   property O ^ prop2;   // OK  
   N * m_p;   // OK  
};  
```
