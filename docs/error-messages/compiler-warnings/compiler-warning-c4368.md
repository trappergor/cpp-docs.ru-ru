---
title: Предупреждение компилятора C4368 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4368
dev_langs:
- C++
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3a7e53c979a3b13bde205a4546c486061a17110
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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