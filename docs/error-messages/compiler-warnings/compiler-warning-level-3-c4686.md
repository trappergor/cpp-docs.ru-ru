---
title: Предупреждение (уровень 3) C4686 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4686
dev_langs:
- C++
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1edbf438951644f63aae637a68f69d173ab7e1b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4686"></a>Предупреждение компилятора (уровень 3) C4686
**'**   
 ***определяемый пользователем тип* ": возможное изменение поведения, изменение возвращаемого значения UDT соглашение о вызовах**  
  
 Специализация шаблона класса не был определен до его использования в возвращаемый тип. Все, что создает экземпляр класса устранить ошибку C4686; объявление экземпляра или доступ к члену (C\<int >:: ничего) также являются параметры.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Вместо этого попробуйте сделать следующее  
  
```  
// C4686.cpp  
// compile with: /W3  
#pragma warning (default : 4686)  
template <class T>  
class C;  
  
template <class T>  
C<T> f(T);  
  
template <class T>  
class C {};  
  
int main() {  
   f(1);   // C4686  
}  
  
template <class T>  
C<T> f(T) {  
   return C<int>();  
}  
```