---
title: "Ошибка компилятора C3861 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3861
dev_langs: C++
helpviewer_keywords: C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82656822d408be4b2fc085abe8a007469c822a65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3861"></a>Ошибка компилятора C3861

> "*идентификатор*": идентификатор не найден  
  
Компилятору не удалось разрешить ссылку на идентификатор даже при поиске с зависимостью от аргументов.  
  
Чтобы устранить эту ошибку, сравните использование *идентификатор* для написания и регистр объявления идентификатора. Убедитесь, что [операторов разрешения области видимости](../../cpp/scope-resolution-operator.md) и пространство имен [директив using](../../cpp/namespaces-cpp.md#using_directives) используются правильно. Если идентификатор объявлен в файле заголовка, убедитесь, что заголовок включен до ссылки на идентификатор. Если идентификатор должен быть видимое извне, убедитесь, что он объявлен в любой исходный файл, который его использует. Также проверьте, что идентификатор объявления или определения не исключен по [директив условной компиляции](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md). 

Изменения, чтобы удалить устаревшие функции из библиотеки времени выполнения C в Visual Studio 2015 могут вызвать C3861. Чтобы устранить эту ошибку, удалите ссылки на эти функции или замените их безопасные альтернативные способы, если таковые имеются. Дополнительные сведения см. в разделе [устаревшие функции](../../c-runtime-library/obsolete-functions.md).  

При появлении ошибки C3861 после миграции проекта из более старых версий компилятора, могут возникнуть проблемы, связанные с поддерживаемых версий Windows. Visual C++ больше не поддерживает создание программ для Windows 95, Windows 98, Windows ME, Windows NT и Windows 2000. Если WINVER и _WIN32_WINNT назначены одной из этих версий Windows, необходимо изменить такие макросы. Дополнительные сведения см. в разделе [изменение WINVER и _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md).
  
## <a name="example"></a>Пример  

Следующий пример приводит к возникновению ошибки C3861, так как идентификатор не определен.  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();    // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>Пример  

Следующий пример приводит к возникновению ошибки C3861, так как идентификатор отображается в области видимости файла его определения, только в том случае, если она не объявлена в других исходных файлах, которые его используют.  
  
```cpp  
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp  
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {  
   std::cout << f() << std::endl;    // C3861
}  
```  
  
```cpp  
// C3861_a2.cpp  
int f() {  // declared and defined here
   return 42;  
}
```  
  
## <a name="example"></a>Пример  

Классы исключений в стандартной библиотеке C++ требует `std` пространства имен.  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```  
## <a name="example"></a>Пример  

Устаревшие функции были удалены из библиотеки CRT.  
  
```cpp  
// C3861_c.cpp  
#include <stdio.h>  
int main() {  
   char line[21]; // room for 20 chars + '\0'  
   gets( line );  // C3861  
   // Use gets_s instead.  
   printf( "The line entered was: %s\n", line );  
}  
```
Следующий пример приводит к возникновению ошибки C3767, поскольку компилятор не может использовать поиск с зависимостью от аргументов для FriendFunc:  
  
```  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3861 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
Чтобы исправить ошибку, объявите friend в области видимости класса и его определения в области видимости пространства имен:  
  

класс MyClass {}  
   int m_private;  
   дружественные func() void;  
};  
  
{void func()  
   MyClass s;  
   s.m_private = 0;  
}  
  
int main() {  
   func();  
}  