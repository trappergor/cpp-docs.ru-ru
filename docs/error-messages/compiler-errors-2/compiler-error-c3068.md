---
title: Ошибка компилятора C3068 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f378a60c79defed4fb1738515ca5b65b2851056
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3068"></a>Ошибка компилятора C3068
«функция»: функция «naked» не может содержать объекты, требующие развертывания при возникновении исключения C++  
  
 Компилятору не удалось выполнить развертывание стека на [naked](../../cpp/naked-cpp.md) функцию, которая создала исключение, так как временный объект был создан в функции и обработку исключений C++ ([/EHsc](../../build/reference/eh-exception-handling-model.md)) был указан.  
  
 Чтобы устранить эту ошибку, выполните по крайней мере одно из следующих действий.  
  
-   Не компилировать с параметром/EHsc.  
  
-   Не следует помечать функцию как `naked`.  
  
-   Не создавайте временный объект в функцию.  
  
 Если функция создает временный объект в стеке, если функция вызывает исключение, и в том случае, если включена обработка исключений C++, компилятор очистит вверх по стеку, если возникает исключение.  
  
 Когда возникает исключение, созданный компилятором код вызывается из пролога и эпилога, а какие не существуют в функции с атрибутом naked, выполняется для функции.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3068:  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```