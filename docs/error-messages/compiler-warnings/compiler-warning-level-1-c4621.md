---
title: "Предупреждение компилятора (уровень 1) C4621 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4621"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4621"
ms.assetid: 40931bd9-cb89-497e-86f0-cec9f016c63c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4621
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не найдена постфиксная форма "оператор \-\-" для типа "тип"; используется префиксная форма  
  
 Отсутствует постфиксный оператор декремента, определенный для данного типа.  Компилятор использовал перегруженный префиксный оператор.  
  
 Это предупреждение можно удалить, определив постфиксный оператор `--`.  Создайте две версии аргументов оператора `--`, как показано ниже:  
  
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