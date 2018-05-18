---
title: Оператор for (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38181a43134c35c4db1db3d78a79d3338934b7d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="for-statement-c"></a>Оператор for (C++)
Повторяет выполнение инструкций (statement), пока условие не станет ложным. Сведения об операторе for для диапазона см. в разделе [Оператор for для диапазона (C++)](../cpp/range-based-for-statement-cpp.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте оператор `for` для создания циклов, которые должны выполняться заданное число раз.  
  
 Оператор `for` состоит из трех необязательных частей, как показано в следующей таблице.  
  
### <a name="for-loop-elements"></a>элементы цикла for  
  
|Название части|Когда выполняется|Описание|  
|-----------------|-------------------|-----------------|  
|`init-expression`|Выражение `init-expression` выполняется только один раз перед любой другой частью инструкции **for**. Затем управление передается `cond-expression`.|Часто используется для инициализации индексов цикла. Может содержать выражения или объявления.|  
|`cond-expression`|Перед выполнением каждой итерации `statement`, включая первую итерацию. `statement` выполняется, только если `cond-expression` имеет значение true (не равное нулю).|Выражение, значение которого относится к целочисленному типу или типу класса, для которого имеется однозначное преобразование к целочисленному типу. Обычно используется для проверки критериев завершения цикла for.|  
|`loop-expression`|В конце каждой итерации `statement`. После выполнения `loop-expression` производится вычисление `cond-expression`.|Обычно используется для приращения индексов цикла.|  
  
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
  
 `init-expression` и `loop-expression` могут содержать несколько операторов, разделенных запятыми. Пример:  
  
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
  
 Цикл `for` завершается, когда в инструкциях тела цикла (`statement`) выполняется оператор [break](../cpp/break-statement-cpp.md), [return](../cpp/return-statement-cpp.md) или [goto](../cpp/goto-statement-cpp.md) (ведущий к оператору с меткой за пределами цикла **for**). Оператор [continue](../cpp/continue-statement-cpp.md) в цикле `for` завершает только текущую итерацию.  
  
 Если выражение `cond-expression` опущено, считается, что его значение истинно, и цикл **for** не завершится, если в `statement` нет `break`, `return` или `goto`.  
  
 Хотя эти три части оператора `for` обычно используются для инициализации, проверки завершения и для наращения, их можно использовать и другими способами.  Например, следующий код выводит числа от 0 до 4. В этом случае в `statement` будет пусто:  
  
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
  
## <a name="for-loops-and-the-c-standard"></a>циклы for и стандарт C++  
 Стандарт C++ указывает, что переменная, объявленная в цикле `for`, должна выйти из области видимости после завершения цикла `for`. Пример:  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
    // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 По умолчанию, при использовании параметра [/Ze](../build/reference/za-ze-disable-language-extensions.md) переменная, объявленная в цикле `for`, остается в области видимости до окончания внешней области видимости, в которой находится цикл `for`.  
  
 [/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) включает поведение объявленных в циклах for переменных по стандарту без необходимости указания /Za.  
  
 Также можно использовать различия области видимости цикла `for` для повторного объявления переменных при /Ze следующим образом:  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 Это более точно имитирует стандартное поведение переменной, объявленной в цикле `for`, что требует выхода переменных, объявленных в цикле `for`, за пределы области видимости после выполнения цикла. При объявлении переменной в цикле `for` компилятор внутри себя превращает ее в локальную переменную внешней области, в которой находится цикл `for`, даже если там уже есть локальная переменная с таким же именем.  
  
## <a name="see-also"></a>См. также  
 [Операторы итерации](../cpp/iteration-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор while (C++)](../cpp/while-statement-cpp.md)   
 [Оператор do-while (C++)](../cpp/do-while-statement-cpp.md)   
 [Оператор for для диапазона (C++)](../cpp/range-based-for-statement-cpp.md)
