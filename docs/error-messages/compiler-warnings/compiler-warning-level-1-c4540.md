---
title: "Предупреждение компилятора (уровень 1) C4540 | Microsoft Docs"
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
  - "C4540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4540"
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

приведение dynamic\_cast использовано для преобразования к недоступной или неоднозначной базе; проверка во время выполнения приведет к ошибке \("тип1" в "тип2"\)  
  
 Для преобразования типов используется приведение `dynamic_cast`.  Выполнение приведения невозможно \(во всех случаях возвращается значение **NULL**\), поскольку базовый класс недоступен \(например объявлен как `private`\) или является неоднозначным \(например определен несколько раз в иерархии классов\).  
  
 Ниже приведен пример этого предупреждения.  Класс **B** является производным от класса **A**.  В результате приведения `dynamic_cast`, используемого в программе для приведения производного класса **B** к классу **A**, всегда возникает ошибка, поскольку класс **B** объявлен как `private` и недоступен.  Чтобы устранить предупреждение, измените уровень доступа класса **A** на **public**.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```