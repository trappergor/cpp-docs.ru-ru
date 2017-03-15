---
title: "Ошибка компилятора C2146 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2146"
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Ошибка компилятора C2146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ошибка синтаксиса: пропущен "токен" перед идентификатором "идентификатор"  
  
 Компилятор рассчитывал обнаружить параметр `token`, но вместо него обнаружил параметр `identifier`.  Возможные причины:  
  
1.  Ошибка правописания или неверно выбран регистр.  
  
2.  Пропущен спецификатор типа в объявлении идентификатора.  
  
 Причиной этой ошибки может быть типографская опечатка.  Как правило, этой ошибке предшествует ошибка [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md).  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C2146.  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## Пример  
 Эта ошибка также может возникнуть в результате изменений работы компилятора в Visual Studio .NET 2003: пропущено ключевое слово `typename`.  
  
 Следующий пример демонстрирует успешную компиляцию в Visual Studio .NET 2002, которую, однако, не удастся выполнить в Visual Studio .NET 2003:  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## Пример  
 Данная ошибка возникает в результате изменений работы компилятора в Visual Studio .NET 2003: явной специализации не удается найти параметры шаблона из первичного шаблона.  
  
 Использование `T` из первичного шаблона недопустимо в явной специализации.  Чтобы сделать код допустимым для версий Visual C\+\+ Visual Studio .NET 2003 и Visual Studio .NET, следует заменить все экземпляры параметра шаблона в специализации на явным образом специализированный тип.  
  
 Следующий пример демонстрирует успешную компиляцию в Visual Studio .NET, которую, однако, не удастся выполнить в Visual Studio .NET 2003:  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```