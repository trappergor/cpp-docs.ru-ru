---
title: "Оператор for (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6b958bba842a5dfdbe61415c6ad81aab7a8b4110
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="for-statement-c"></a>Оператор for (C++)
Выполняет оператор повторно до тех пор, пока условное значение не станет false. Сведения на основе диапазонов для инструкции см. в разделе [инструкции (C++) на основе диапазонов](../cpp/range-based-for-statement-cpp.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте оператор `for` для создания циклов, которые должны выполняться заданное число раз.  
  
 Оператор `for` состоит из трех необязательных частей, как показано в следующей таблице.  
  
### <a name="for-loop-elements"></a>элементы цикла for  
  
|Имя синтаксиса|Когда выполняется|Описание|  
|-----------------|-------------------|-----------------|  
|`init-expression`|Перед любой другой элемент **для** инструкции `init-expression` выполняется только один раз. Затем управление передается `cond-expression`.|Часто используется для инициализации индексов цикла. Может содержать выражения или объявления.|  
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
  
 `init-expression` и `loop-expression` могут содержать несколько операторов, разделенных запятыми. Например:  
  
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
  
 Объект `for` цикл завершается, когда [разрыв](../cpp/break-statement-cpp.md), [возвращают](../cpp/return-statement-cpp.md), или [goto](../cpp/goto-statement-cpp.md) (к оператору с меткой за пределами **для** цикл) в `statement` выполняется. Объект [Продолжить](../cpp/continue-statement-cpp.md) инструкции в `for` цикла завершает только текущую итерацию.  
  
 Если `cond-expression` будет указано, оно считается равным true и **для** цикл не завершится без `break`, `return`, или `goto` в `statement`.  
  
 Хотя эти три поля оператора `for` обычно используются для инициализации, тестирования на завершение и увеличения, они не ограничиваются такими способами использования. Например, следующий код выводит числа от 0 до 4. В данном случае `statement` является оператором null:  
  
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
  
 По умолчанию в разделе [/Ze](../build/reference/za-ze-disable-language-extensions.md), переменной, объявленной в `for` цикла остается в области до `for` цикла внешней области.  
  
 [/ Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) включает стандартное поведение переменных, объявленных в циклах for, без необходимости указания/Za.  
  
 Также можно использовать различия области видимости цикла `for` для повторного объявления переменных в /Ze следующим образом:  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 Это более точно имитирует стандартное поведение переменной, объявленной в цикле `for`, что требует выхода переменных, объявленных в цикле `for`, за пределы области видимости после выполнения цикла. Если переменная объявлена в цикле `for`, компилятор внутренним образом повышает ее до локальной переменной во внешней области цикла `for`, даже если там уже есть локальная переменная с тем же именем.  
  
## <a name="see-also"></a>См. также  
 [Операторы итерации](../cpp/iteration-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор while (C++)](../cpp/while-statement-cpp.md)   
 [Оператор do-while (C++)](../cpp/do-while-statement-cpp.md)   
 [Основанный на диапазоне оператор for (C++)](../cpp/range-based-for-statement-cpp.md)
