---
title: "Отсутствует тело функции или переменная | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "основная часть функции"
  - "переменные, отсутствует"
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Отсутствует тело функции или переменная
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Компилятор может продолжать работу с прототипом функции без ошибок, но компоновщику не удается распознать вызов адреса, поскольку код функции или переменная интервала зарезервированы.  Эту ошибку не удастся увидеть до создания вызова функции, которую должен разрешить компоновщик.  
  
## Пример  
 В целом, вызов функции приводит к появлению ошибки LNK2019, поскольку наличие прототипа позволяет компилятору считать, что функция существует.  Компоновщик обнаруживает отсутствие функции.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## Пример  
 Убедитесь в том, что реализация указанной функции в языке C\+\+ включена для класса, а не только для прототипа в определении класса.  При определении класса за пределами файла заголовка необходимо включить имя класса перед функцией \(`Classname``::``memberfunction`\).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## См. также  
 [Ошибка средств компоновщика LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md)