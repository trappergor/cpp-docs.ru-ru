---
title: Предупреждение (уровень 1) C4621 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4621
dev_langs:
- C++
helpviewer_keywords:
- C4621
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efefe6feacd79833e3ec51cc1f2274c142b2426a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281954"
---
# <a name="compiler-warning-level-1-c4621"></a>Предупреждение компилятора (уровень 1) C4621
не постфиксная форма «operator--» для типа «тип»; используется префиксная форма  
  
 Произошла постфиксный оператор декремента, определенные для данного типа. Компилятор использовал перегруженный префиксный оператор.  
  
 Это предупреждение можно избежать, определив постфиксный `--` оператор. Создать версию с двумя аргументами `--` оператора, как показано ниже:  
  
```  
// C4621.cpp  
// compile with: /W1  
class A  
{  
public:  
   A(int nData) : m_nData(nData)  
   {  
   }  
  
   A operator--()  
   {  
      m_nData -= 1;  
      return *this;  
   }  
  
   // A operator--(int)  
   // {  
   //    A tmp = *this;  
   //    m_nData -= 1;  
   //    return tmp;  
   // }  
  
private:  
   int m_nData;  
};  
  
int main()  
{  
   A a(10);  
   --a;  
   a--;   // C4621  
}  
```