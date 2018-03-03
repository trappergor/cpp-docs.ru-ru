---
title: "Предупреждение (уровень 1) C4383 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4383
dev_langs:
- C++
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a7c478783c7f908125de7b97a1d21a9f1ece029
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4383"></a>Предупреждение компилятора (уровень 1) C4383
«оператор_разыменовывания_экземпляра»: значение разыменования дескриптора может измениться, если существует определенный пользователем оператор» оператор "; Запишите оператор как статическую функцию, чтобы сделать его явным по отношению к операнду  
  
 При добавлении переопределения экземпляр определяемого пользователем оператора разыменования в управляемом типе, потенциально переопределяется возможность возвращать объекта дескриптора типа оператор разыменования. Рассмотрите возможность написания статического определяемого пользователем оператора разыменования.  
  
 Дополнительные сведения см. в разделе [оператор дескриптора объекта (^)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) и [оператор отслеживания ссылок](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
 Кроме того оператор экземпляра не доступны в другие компиляторы языка через метаданные, на которую указывает ссылка. Дополнительные сведения см. в разделе [определяемые пользователем операторы (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4383.  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```