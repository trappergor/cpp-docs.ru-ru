---
title: "Ошибка компилятора C2593 | Microsoft Docs"
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
  - "C2593"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2593"
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2593
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неоднозначный "идентификатор оператора"  
  
 Для перегруженного оператора определено несколько возможных операторов.  
  
 Данную ошибку можно исправить, если использовать явное приведение для одного или нескольких фактических параметров.  
  
 Следующий пример приводит к возникновению ошибки C2593:  
  
```  
// C2593.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
void operator+( X, X );  
void operator+( A, B );  
D d;  
  
int main() {  
   d +  d;         // C2593, D has an A, B, and X   
   (X)d + (X)d;    // OK, uses operator+( X, X )  
}  
```  
  
 Данная ошибка может возникнуть в результате сериализации переменной с плавающей точкой с использованием объекта `CArchive`.  Компилятор определяет оператор `<<` как неоднозначный.  Единственными простыми типами C\+\+, сериализацию которых может выполнить `CArchive`, являются типы фиксированного размера `BYTE`, `WORD`, `DWORD` и `LONG`.  Все целочисленные типы должны быть приведены к одному из данных типов для сериализации.  Типы с плавающей точкой должны быть архивированы с помощью функции\-члена `CArchive::Write()`.  
  
 В следующем примере показано как архивировать переменную с плавающей точкой \(`f`\) в архив `ar`:  
  
```  
ar.Write(&f, sizeof( float ));  
```