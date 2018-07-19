---
title: Ошибка компилятора C2593 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2593
dev_langs:
- C++
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e419416266e0e3c4ebff8190b3b26b1c43c9ba0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229889"
---
# <a name="compiler-error-c2593"></a>Ошибка компилятора C2593
«Идентификатор оператора» является неоднозначным  
  
 Существует несколько возможных оператор определен для перегруженного оператора.  
  
 Чтобы устранить эту ошибку, используйте явное приведение на один или несколько фактических параметров.  
  
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
  
 Эта ошибка может быть вызвана сериализации с плавающей запятой переменной с помощью `CArchive` объекта. Компилятор определяет `<<` оператор неопределенности. Типами C++ только типы-примитивы, `CArchive` можно сериализовать типы фиксированного размера `BYTE`, `WORD`, `DWORD`, и `LONG`. Все целочисленные типы необходимо привести к одному из этих типов для сериализации. Типы с плавающей запятой необходимо архивировать с помощью `CArchive::Write()` функции-члена.  
  
 В следующем примере показано, как архивировать переменную с плавающей запятой (`f`) архив `ar`:  
  
```  
ar.Write(&f, sizeof( float ));  
```