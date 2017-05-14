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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 9a0c25772fadec86a893b8c7c4af09072eb0476f
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-3-c4996"></a>Предупреждение компилятора предупреждение (уровень 3) C4996
Компилятор обнаружил устаревшее объявление.  
  
Предупреждение или ошибка имеет несколько возможных значений, в зависимости от контекста.  
  
Предупреждение C4996 возникает, когда компилятор обнаруживает функцию или переменную, которая отмечена как [устаревшими](../../cpp/deprecated-cpp.md) с помощью `__declspec(deprecated)` модификатор. Это предупреждение также выдается при попытке доступа к функции, член класса или определение типа, которое имеет C ++ 14 `[[deprecated]]` атрибута. Дополнительные сведения см. в разделе [стандартные атрибуты C++](../../cpp/attributes2.md). Можно использовать этот атрибут самостоятельно в библиотеках, чтобы предупредить клиентов о нерекомендуемых функций, члены и определения типов.  
  
Ряд функций, функций-членов, функций шаблонов и глобальных переменных в библиотеках Visual Studio помечены как устаревшие. Эти функции могут содержать разные предпочтительные имена, могут быть небезопасными или иметь более безопасный вариант либо могут быть устаревшими. Многие сообщения об ошибках входить предложенная замена устаревшей функции или глобальной переменной.  
  
Чтобы устранить эту проблему, обычно рекомендуется изменить код, чтобы вместо этого используйте предложенные более безопасным или обновленные функции и глобальные переменные. Если необходимо использовать в целях обеспечения переносимости существующих функций и переменных, предупреждение можно отключить.  
  
Предупреждение для определенной строки кода, можно отключить с помощью [предупреждение](../../preprocessor/warning.md) pragma `#pragma warning(suppress : 4996)`. Можно отключить его в файле с помощью директивы #pragma warning `#pragma warning(disable : 4996)`. Можно отключить его глобально в сборках командной строки с помощью **/wd4996** параметр командной строки. Чтобы отключить предупреждения для проекта в Интегрированной среде разработки Visual Studio, откройте **страницы свойств** диалогового окна выберите **свойства конфигурации**, **C/C++**, **Дополнительно** страницы и изменение **отключить определенные предупреждения** свойство для добавления `4996`.  Можно также использовать макросы препроцессора для отключения определенных определенных классов предупреждений о нерекомендуемых функциях используются в библиотеках. Ниже приводится описание этих макросов.  
  
Ниже перечислены источники библиотеки C4996.  
  
## <a name="posix-function-names"></a>Имена POSIX-функция  
  
**Имя POSIX для этого элемента устарело. Используйте имя, соответствующее стандарту ISO C и C++:** *новое_имя*. **Подробные сведения см.**  
  
Корпорация Майкрософт переименовать некоторые функции POSIX в CRT для соответствия C99 и C ++ 03 для имен глобальных функций, определяемого реализацией. Только исходные имена POSIX устарели, не сами функции. В большинстве случаев к имени функции POSIX добавляется символ подчеркивания в начале, чтобы создать имя, соответствующее стандартам. Компилятор выдает предупреждение об устаревании первоначальное имя функции и предлагает предпочтительное имя.  
  
Чтобы устранить эту проблему, обычно рекомендуется изменить код, чтобы вместо этого используйте имена функций, предлагаемых. Тем не менее обновленные имена зависят от корпорации Майкрософт. Если необходимо использовать существующие имена функций в целях обеспечения переносимости можно отключить эти предупреждения. Функции POSIX по-прежнему доступны в библиотеке в первоначальные имена.  
  
Чтобы отключить предупреждения об устаревании для этих функций, задайте макрос препроцессора **_CRT_NONSTDC_NO_WARNINGS**. Вы можете сделать это в командной строке, включив параметр `/D_CRT_NONSTDC_NO_WARNINGS`. Чтобы задать этот макрос в Visual Studio, откройте диалоговое окно **Страницы свойств** проекта. Разверните узел **Свойства конфигурации**, **C/C++**, **Препроцессор**. В окне **Определения препроцессора**добавьте `_CRT_NONSTDC_NO_WARNINGS`. Нажмите кнопку **ОК** для сохранения изменений, а затем выполните повторную сборку проекта. Чтобы задать этот макрос только в определенных файлах с исходным кодом, добавьте строку `#define _CRT_NONSTDC_NO_WARNINGS` перед любой строкой, которая включает файл заголовка.  
  
## <a name="unsafe-crt-library-functions"></a>Небезопасные функции библиотеки CRT  
  
 **Эта функция или переменная может быть небезопасным. Рассмотрите возможность использования***safe_version* **вместо него.   Чтобы отключить сообщения об устаревании, используйте _CRT_SECURE_NO_WARNINGS.  See online help for details.** (Функция или переменная может быть небезопасной. Используйте strncpy_s. Дополнительные сведения см. в справке.)  
  
 Корпорация Майкрософт рекомендуется к использованию некоторые функции CRT и стандартной библиотеки C++ и глобальные объекты были заменены более безопасные версии. В большинстве случаев устаревшие функции позволяют буферы, которые может привести к проблемам безопасности серьезные unchecked чтения или записи. Компилятор выдает предупреждение об устаревании для этих функций и предлагает предпочтительную функцию.  
  
 Чтобы устранить эту проблему, рекомендуется использовать функцию или переменную *safe_version* вместо него. Если вы убедились, что невозможно для перезаписи буфера или overread в коде и не может изменить код в целях обеспечения переносимости, можно отключить это предупреждение.  
   
 Чтобы отключить предупреждения об устаревании для этих функций в CRT, задайте **_CRT_SECURE_NO_WARNINGS**. Чтобы отключить предупреждения об устаревших глобальных переменных, задайте **_CRT_SECURE_NO_WARNINGS_GLOBALS**. Дополнительные сведения об этих устаревших функциях и глобальных переменных см. в разделе [средства безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md) и [безопасные библиотеки: стандартная библиотека C++](../../standard-library/safe-libraries-cpp-standard-library.md).  
  
## <a name="unsafe-standard-library-functions"></a>Небезопасные функции стандартной библиотеки  
  
 **"std::** *function_name* **::\_Unchecked\_итераторы::\_Deprecate" вызов std::** *имя_функции* **с параметрами, которые могут быть небезопасными - этот вызов зависит от вызывающего объекта, чтобы проверить правильность переданных значений. Чтобы отключить это предупреждение, используйте -D_SCL_SECURE_NO_WARNINGS. См. в документации по использованию «Проверяемых итераторов» Visual C++**  
  
Это предупреждение появляется в отладочных построениях, поскольку определенные функции стандартной библиотеки C++ не проверяют правильность параметров. В большинстве случаев это, поскольку недостаточно сведений для функции для проверки границ контейнера или итераторы, можно использовать неправильно с функцией. Это предупреждение помогает определить эти функции используется, поскольку они могут быть источником уязвимости в программе. Для получения дополнительной информации см. [Checked Iterators](../../standard-library/checked-iterators.md).  
  
Например, это предупреждение появляется в режиме отладки, если передать указатель на элемент в `std::copy` вместо простой массива. Чтобы устранить эту проблему, используйте массив соответствующим образом объявленный, библиотеку можно проверить массив экстентов и выполнять проверка границ.  
  
```cpp  
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>
 
void example(char const * const src) { 
    char dest[1234]; 
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996 
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements 
} 
```  
  
Несколько алгоритмов стандартной библиотеки были обновлены в C ++ 14 доступны версии «два диапазона». При использовании двух диапазон версий второго диапазона предоставляет необходимые проверка границ:  
  
```cpp  
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>
 
bool example(
    char const * const left, 
    const size_t leftSize, 
    char const * const right, 
    const size_t rightSize) 
{ 
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead: 
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK 
    return result;
}
```  
  
В этом примере демонстрируется несколько дополнительных возможностей, стандартная библиотека может использоваться для проверки использования итератора и если снят флажок использования может быть опасной:  
  
```cpp  
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
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
    // (i.e. an overrun triggers a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    // NOTE: This applies only when raw arrays are 
    // given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun triggers undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun triggers a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), 
        stdext::make_checked_array_iterator(p7, 16), 
        [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator 
    // is marked as checked in debug mode, but it performs no checking, 
    // so an overrun triggers undefined behavior  
    int a8[16];  
    int * p8 = a8;  
    transform( v.begin(), v.end(), 
        stdext::make_unchecked_array_iterator(p8), 
        [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
```  
  
Если вы убедились, что код не может иметь ошибка в функции стандартной библиотеки, которые к выводу предупреждения переполнение буфера, можно отключить это предупреждение. Чтобы отключить предупреждения для этих функций, задайте **_SCL_SECURE_NO_WARNINGS**.   
  
## <a name="example-checked-iterators-enabled"></a>Пример: Итераторы включена  
  
Предупреждение C4996 также может возникать при проверяемый итератор не используется при компиляции с параметром `_ITERATOR_DEBUG_LEVEL` определяется как 1 или 2. Он имеет значение 2 по умолчанию для сборок в режиме отладки или значение 0 для коммерческие сборки. Дополнительные сведения см. в разделе [Checked Iterators](../../standard-library/checked-iterators.md) .  
  
```cpp  
// C4996_checked.cpp  
// compile with: /EHsc /W4 /MDd C4996_checked.cpp  
#define _ITERATOR_DEBUG_LEVEL 2  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead:  
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
```  
  
## <a name="unsafe-mfc-or-atl-code"></a>Код небезопасный MFC или ATL  
  
Предупреждение C4996 также может возникать при использовании функций библиотек MFC или ATL, устаревшие по соображениям безопасности.  
  
Чтобы устранить эту проблему, настоятельно рекомендуется изменить код, чтобы вместо этого используйте обновленных функций.  
  
Сведения о том, как отключить эти предупреждения см. в разделе [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings) и [_ATL_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73).  
  
## <a name="obsolete-crt-functions-and-variables"></a>Устаревшие функции CRT и переменные  
  
**Эта функция или переменная была заменена более новой функции библиотеки или операционной системы. Рассмотрите возможность использования** *new_item* **вместо него. See online help for details.** (Функция или переменная может быть небезопасной. Используйте strncpy_s. Дополнительные сведения см. в справке.)  
  
Некоторые функции и глобальные переменные библиотеки устарели. Эти функции и переменные могут быть удалены в будущей версии библиотеки. Компилятор выдает предупреждение об устаревании для этих элементов и предлагает предпочтительную альтернативу.  
  
Чтобы устранить эту проблему, мы рекомендуем изменить код, чтобы использовать предлагаемый функции или переменной.  
  
Чтобы отключить предупреждения об устаревании для этих элементов, задайте **_CRT_OBSOLETE_NO_WARNINGS**. Дополнительные сведения см. в документации по устаревшей функции или переменной.  
  
## <a name="example-marshalling-errors-in-clr-code"></a>Пример: Ошибки маршалинга в коде среды CLR  
  
Предупреждение C4996 также может возникать при использовании библиотеки маршалинга среды CLR. В этом случае C4996 будет ошибкой, а не предупреждением. Эта ошибка возникает при использовании [marshal_as](../../dotnet/marshal-as.md) для преобразования между двумя типами данных, требующих [класс marshal_context](../../dotnet/marshal-context-class.md). Эта ошибка может также возникать, когда библиотека маршалинга не поддерживает преобразование. Дополнительные сведения о библиотеке маршалинга см. в статье [Overview of Marshaling in C++](../../dotnet/overview-of-marshaling-in-cpp.md).  
  
Этот пример приводит к возникновению предупреждения C4996, поскольку библиотеке маршалинга требуется контекст для преобразования из `System::String` для `const char *`.  
  
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
  
## <a name="example-user-defined-deprecated-function"></a>Пример: Пользовательской устаревшие функции  
  
Предупреждения об вызывающим объектам использовать некоторые функции больше не рекомендуется, можно использовать устаревший атрибут в собственном коде. В этом примере C4996 возникает в строке, в котором объявлена устаревшей функции и для строки, в которой используется функция.  
  
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
   func1(1);    // C4996  
}  
```  
  

