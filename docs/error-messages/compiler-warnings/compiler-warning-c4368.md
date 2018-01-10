---
title: "Предупреждение компилятора C4368 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4368
dev_langs: C++
helpviewer_keywords: C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9694eb05a2d14ff8dac49c0e9a3cb29dcf52bbac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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