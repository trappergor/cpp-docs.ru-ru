---
title: Предупреждение (уровень 1) C4383 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4383
dev_langs:
- C++
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b78209cf4e3e320cca8b161a4e6c99eaca6d771c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286088"
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