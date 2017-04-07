---
title: "Предупреждение (уровень 3) C4996 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: aa9586bd0abed0b1fa1d24c777eea8c82c5cedc0
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-warning-level-3-c4996"></a>Предупреждение компилятора предупреждение (уровень 3) C4996
Компилятор обнаружил устаревшее объявление.  
  
 Это предупреждение или ошибка могут означать несколько вещей.  
  
 `C4996`возникает, когда компилятор обнаруживает функцию или переменную, которая отмечена как [устаревшими](../../cpp/deprecated-cpp.md). Ряд функций, функций-членов, функций шаблонов и глобальных переменных в библиотеках Visual Studio помечены как устаревшие. Эти функции могут содержать разные предпочтительные имена, могут быть небезопасными или иметь более безопасный вариант либо могут быть устаревшими. В сообщение об ошибке может входить предложенная замена устаревшей функции или глобальной переменной. Вы можно отключить это предупреждение с [предупреждение](../../preprocessor/warning.md) pragma или **/wd4996** параметр командной строки. Вы можете также использовать макросы препроцессора для отключения определенных классов предупреждений об устаревании. 

Это предупреждение также выдается при попытке доступа к функции, член класса или определение типа, которое имеет C ++ 14 `[[deprecated]]` атрибута. Дополнительные сведения см. в разделе [стандартные атрибуты C++](../../cpp/attributes2.md). 
  
 **Имя POSIX для этого элемента устарело. Используйте имя, соответствующее стандарту ISO C и C++:** новое_имя**. See online help for details.** (Функция или переменная может быть небезопасной. Используйте strncpy_s. Дополнительные сведения см. в справке.)  
  
 Некоторые функции POSIX в CRT были переименованы для соответствия правилам C99 и C++03 для имен глобальных функций, задаваемых в реализации. В большинстве случаев к имени функции POSIX добавляется символ подчеркивания в начале, чтобы создать имя, соответствующее стандартам. Компилятор выдает предупреждение об устаревании для исходных имен функций и предлагает предпочтительное имя. Устаревают только исходные имена, а не сами функции. Чтобы отключить предупреждения об устаревании для этих функций, задайте макрос препроцессора **_CRT_NONSTDC_NO_WARNINGS**. Вы можете сделать это в командной строке, включив параметр `/D_CRT_NONSTDC_NO_WARNINGS`. Чтобы задать этот макрос в Visual Studio, откройте диалоговое окно **Страницы свойств** проекта. Разверните узел **Свойства конфигурации**, **C/C++**, **Препроцессор**. В окне **Определения препроцессора**добавьте `_CRT_NONSTDC_NO_WARNINGS`. Нажмите кнопку **ОК** для сохранения изменений, а затем выполните повторную сборку проекта. Чтобы задать этот макрос только в определенных файлах с исходным кодом, добавьте строку `#define _CRT_NONSTDC_NO_WARNINGS` перед любой строкой, которая включает файл заголовка.  
  
 **Эта функция или переменная может быть небезопасным. Рассмотрите возможность использования** safe_version **вместо него. Чтобы отключить сообщения об устаревании, используйте _CRT_SECURE_NO_WARNINGS.  See online help for details.** (Функция или переменная может быть небезопасной. Используйте strncpy_s. Дополнительные сведения см. в справке.)  
  
 Некоторые функции CRT и стандартной библиотеки C++ и глобальные переменные устарели им следует предпочесть новые, более безопасные функции. Компилятор выдает предупреждение об устаревании для этих функций и предлагает предпочтительную функцию. Чтобы отключить предупреждения об устаревании для этих функций в CRT, задайте **_CRT_SECURE_NO_WARNINGS**. Чтобы отключить предупреждения об устаревших глобальных переменных, задайте **_CRT_SECURE_NO_WARNINGS_GLOBALS**. Дополнительные сведения об этих устаревших функциях и глобальных переменных см. в разделе [средства безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md) и [безопасные библиотеки: стандартная библиотека C++](../../standard-library/safe-libraries-cpp-standard-library.md).  
  
 **Вызов функции с параметрами, которые могут быть небезопасными - этот вызов зависит от вызывающего объекта, чтобы проверить правильность переданных значений. Чтобы отключить это предупреждение, используйте -D_SCL_SECURE_NO_WARNINGS. См. в документации по использованию «Проверяемых итераторов» Visual C++**  
  
 Определенные функции стандартной библиотеки C++ не проверяют правильность параметров. Это предупреждение позволяет выявить использование таких функций. Чтобы отключить предупреждения для этих функций, задайте **_SCL_SECURE_NO_WARNINGS**. Дополнительные сведения см. в разделе [Проверенные итераторы](../../standard-library/checked-iterators.md).  
  
 **Эта функция или переменная была заменена более новой функции библиотеки или операционной системы. Рассмотрите возможность использования** new_item **вместо него. See online help for details.** (Функция или переменная может быть небезопасной. Используйте strncpy_s. Дополнительные сведения см. в справке.)  
  
 Некоторые функции и глобальные переменные библиотеки устарели. Эти функции и переменные могут быть удалены в будущей версии библиотеки. Компилятор выдает предупреждение об устаревании для этих элементов и предлагает предпочтительную альтернативу. Чтобы отключить предупреждения об устаревании для этих элементов, задайте **_CRT_OBSOLETE_NO_WARNINGS**. Дополнительные сведения см. в документации по устаревшей функции или переменной.  
  
 **Различные сообщения в коде MFC или ATL**  
  
 Предупреждение `C4996` также может возникать при использовании функций библиотек MFC или ATL, не рекомендуемых к использованию по соображениям безопасности. Чтобы подавить эти предупреждения, в разделе [_AFX_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/97dcfd41-1e56-41d5-bf7e-d240b950134b) и [_ATL_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73).  
  
 **Ошибки маршалинга в коде среды CLR**  
  
 Предупреждение `C4996` также может возникать и при использовании библиотеки маршалинга. В этом случае C4996 будет ошибкой, а не предупреждением. Эта ошибка возникает при использовании [marshal_as](../../dotnet/marshal-as.md) для преобразования между двумя типами данных, требующих [класс marshal_context](../../dotnet/marshal-context-class.md). Также эта ошибка будет возникать в случае, когда библиотека маршалинга не поддерживает преобразование. Дополнительные сведения о библиотеке маршалинга см. в разделе [Обзор из маршалировании в C++](../../dotnet/overview-of-marshaling-in-cpp.md).  
  
 **Примеры, создающие C4996**  
  
 В первом примере предупреждение `C4996` возникает в строке, в которой объявляется функция, и в строке, в которой эта функция используется.  
  
## <a name="example"></a>Пример  
 Следующий пример создает C4996.  
  
```cpp  
// C4996.cpp  
// compile with: /W3  
// C4996 warning expected  
#include <stdio.h>  
  
// #pragma warning(disable : 4996)  
void func1(void) {  
   printf_s("\nIn func1");  
}  
  
__declspec(deprecated) void func1(int) {  
   printf_s("\nIn func2");  
}  
  
int main() {  
   func1();  
   func1(1);  
}  
```  
  
## <a name="example"></a>Пример  
 Предупреждение C4996 также может возникнуть, если при компиляции с определенным параметром `_ITERATOR_DEBUG_LEVEL` (по умолчанию для сборок в режиме отладки устанавливается значение 1) не используются проверяемые итераторы.  Дополнительные сведения см. в разделе [Проверяемые итераторы](../../standard-library/checked-iterators.md).  
  
 В следующем примере кода стандартной библиотеки C++ вызывает появление ошибки C4996.  
  
```cpp  
// C4996_b.cpp  
// compile with: /EHsc /W3 /c  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead  
    //   copy(a, a + 3, b);  
    copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
  
```  
  
## <a name="example"></a>Пример  
 В следующем примере кода стандартной библиотеки C++ вызывает появление ошибки C4996 как предупреждение. Комментарии приведены в коде.  
  
```cpp  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (i.e. it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению предупреждения C4996, поскольку библиотеке маршалинга для преобразования из `System::String` в `const char *`требуется контекст.  
  
```cpp  
// C4996_Marshal.cpp  
// compile with: /clr   
// C4996 expected  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = marshal_as<const char*>( message );  
   return 0;  
}  
```
