---
title: Ошибка компилятора C2768 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2768
dev_langs:
- C++
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ee0fd3fa213639e70199cfe5653ee2034bc39b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2768"></a>Ошибка компилятора C2768
«функция»: Недопустимое использование явных аргументов шаблона  
  
 Компилятору не удалось определить, если определение функции должна быть явной специализации шаблона функции или определении функции должна быть новой функции.  
  
 Эта ошибка появилась в Visual Studio .NET 2003 в составе усовершенствований согласованности компилятора.  
  
 Следующий пример приводит к возникновению ошибки C2768:  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```