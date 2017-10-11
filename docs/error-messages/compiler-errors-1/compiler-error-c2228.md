---
title: "Ошибка компилятора C2228 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2228
dev_langs:
- C++
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6960d2a34a6a68925e04e0812730025d1ce2ff92
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2228"></a>Ошибка компилятора C2228
слева от ".identifier" должен быть указан класс, структура или объединение  
  
 Операнд слева от точки (.) не класса, структуры или объединения.  
  
 Следующий пример приводит к возникновению ошибки C2228:  
  
```  
// C2228.cpp  
int i;  
struct S {  
public:  
    int member;  
} s, *ps = &s;  
  
int main() {  
   i.member = 0;   // C2228 i is not a class type  
   ps.member = 0;  // C2228 ps is a pointer to a structure  
  
   s.member = 0;   // s is a structure type  
   ps->member = 0; // ps points to a structure S  
}  
```  
  
 Эта ошибка также возникает из-за неправильного синтаксиса при использовании управляемых расширений. В то время как в других языках Visual Studio для доступа к члену управляемого класса можно использовать оператор "точка", в C++ указатель на объект означает, что для доступа к члену вы должны использовать оператор ->:  
  
 Неправильно: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`  
  
 Правильно: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
