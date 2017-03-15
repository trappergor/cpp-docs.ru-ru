---
title: "Оператор for (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for - ключевое слово [C++]"
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор for (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполняет оператор повторно до тех пор, пока условное значение не станет false.  Сведения об основанном на диапазоне операторе for см. в разделе [Основанное на диапазоне выражение for \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md).  
  
## Синтаксис  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## Заметки  
 Используйте оператор `for` для создания циклов, которые должны выполняться заданное число раз.  
  
 Оператор `for` состоит из трех необязательных частей, как показано в следующей таблице.  
  
### элементы цикла for  
  
|Имя синтаксиса|Когда выполняется|Описание|  
|--------------------|-----------------------|--------------|  
|`init-expression`|Перед любым другим элементом оператора **for** `init-expression` выполняется только один раз.  Затем управление передается `cond-expression`.|Часто используется для инициализации индексов цикла.  Может содержать выражения или объявления.|  
|`cond-expression`|Перед выполнением каждой итерации `statement`, включая первую итерацию.  `statement` выполняется, только если `cond-expression` имеет значение true \(не равное нулю\).|Выражение, значение которого относится к целочисленному типу или типу класса, для которого имеется однозначное преобразование к целочисленному типу.  Обычно используется для проверки критериев завершения цикла for.|  
|`loop-expression`|В конце каждой итерации `statement`.  После выполнения `loop-expression` производится вычисление `cond-expression`.|Обычно используется для приращения индексов цикла.|  
  
 Следующие примеры демонстрируют различные способы использования оператора `for`.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    // The counter variable can be declared in the init-expression.  
    for (int i = 0; i < 2; i++ ){   
       cout << i;  
    }  
    // Output: 01  
    // The counter variable can be declared outside the for loop.  
    int i;  
    for (i = 0; i < 2; i++){  
        cout << i;  
    }  
    // Output: 01  
    // These for loops are the equivalent of a while loop.  
    i = 0;  
    while (i < 2){  
        cout << i++;  
    }  
}  
    // Output: 012  
```  
  
 `init-expression` и `loop-expression` могут содержать несколько операторов, разделенных запятыми.  Например:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
    int i, j;  
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {  
        cout << "i + j = " << (i + j) << '\n';  
    }  
}  
    // Output:  
    i + j = 15  
    i + j = 17  
    i + j = 19  
```  
  
 `loop-expression` можно увеличить или уменьшить, или изменить другими способами.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
for (int i = 10; i > 0; i--) {  
        cout << i << ' ';  
    }  
    // Output: 10 9 8 7 6 5 4 3 2 1  
    for (int i = 10; i < 20; i = i+2) {  
        cout << i << ' ';  
    }  
    // Output: 10 12 14 16 18  
```  
  
 Цикл `for` завершается, когда выполняется [break](../cpp/break-statement-cpp.md), [return](../Topic/return%20Statement%20\(C++\).md) или [goto](../cpp/goto-statement-cpp.md) \(к оператору с меткой за пределами цикла **for**\) в пределах `statement`.  Оператор [continue](../cpp/continue-statement-cpp.md) в цикле `for` завершает только текущую итерацию.  
  
 Если `cond-expression` опускается, его значение считается равным true и цикл **for** не завершится без использования `break`, `return` или `goto` в `statement`.  
  
 Хотя эти три поля оператора `for` обычно используются для инициализации, тестирования на завершение и увеличения, они не ограничиваются такими способами использования.  Например, следующий код выводит числа от 0 до 4.  В данном случае `statement` является оператором null:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    int i;  
    for( i = 0; i < 5; cout << i << '\n', i++){  
        ;  
    }  
}  
```  
  
## циклы for и стандарт C\+\+  
 Стандарт C\+\+ указывает, что переменная, объявленная в цикле `for`, должна выйти из области видимости после завершения цикла `for`.  Например:  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 По умолчанию в [\/Ze](../build/reference/za-ze-disable-language-extensions.md) переменная, объявленная в цикле `for`, остается в области видимости, пока не будут завершены операции внешней области цикла `for`.  
  
 [\/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) включает стандартное поведение переменных, объявленных в циклах for, без необходимости указания \/Za.  
  
 Также можно использовать различия области видимости цикла `for` для повторного объявления переменных в \/Ze следующим образом:  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 Это более точно имитирует стандартное поведение переменной, объявленной в цикле `for`, что требует выхода переменных, объявленных в цикле `for`, за пределы области видимости после выполнения цикла.  Если переменная объявлена в цикле `for`, компилятор внутренним образом повышает ее до локальной переменной во внешней области цикла `for`, даже если там уже есть локальная переменная с тем же именем.  
  
## См. также  
 [Операторы перебора](../cpp/iteration-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Оператор while \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [Выражение do\-while \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [Основанное на диапазоне выражение for \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md)