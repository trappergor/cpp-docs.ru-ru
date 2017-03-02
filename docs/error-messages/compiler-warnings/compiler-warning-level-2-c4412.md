---
title: "Предупреждение (уровень 2) C4412 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 92aa12514088d0fbffbe826a495d76b49ab311d1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4412"></a>Предупреждение компилятора (уровень 2) C4412
«функция»: подпись функции содержит тип «тип»; Объекты C++ небезопасно передавать между чистый код и смешанного или основного.  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015.  
  
 Компилятор обнаружил потенциально небезопасную ситуацию, которая может привести к ошибке выполнения: вызов выполняется из **/CLR: pure** компилируемого объекта функции, импортированной с помощью dllimport, а также подпись функции содержит небезопасный тип. Тип является небезопасным, если он содержит функцию-член или член данных, небезопасный тип или косвенное обращение к нему.  
  
 Это является небезопасным из-за различия в вызовах соглашения между чистого и машинного кода по умолчанию (или смешанного машинного и управляемого). При импорте (через `dllimport`) функция в **/CLR: pure** единице компиляции, убедитесь, что объявления каждого типа в сигнатуре идентичны в единице компиляции, который экспортирует функцию (проявляя особую осторожность о различиях в неявные соглашения о вызовах).  
  
 Виртуальная функция-член зачастую может привести к непредвиденным результатам.  Тем не менее даже невиртуальной функции следует тестировать, чтобы обеспечить получение правильных результатов. Если вы уверены, что вы получаете правильные результаты, можно игнорировать это предупреждение.  
  
 Дополнительные сведения о **/CLR: чисто**, см. [как: переход на/CLR: pure (C + +/ CLI)](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
 C4412 по умолчанию отключено. В разделе [компилятора предупреждения, — это отключение по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) и [dllexport, dllimport](../../cpp/dllexport-dllimport.md) подробнее.  
  
 Чтобы устранить это предупреждение, удалите все функции из типа.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4412.  
  
```  
// C4412.cpp  
// compile with: /c /W2 /clr:pure  
#pragma warning (default : 4412)  
  
struct Unsafe {  
   virtual void __cdecl Test();  
};  
  
struct Safe {  
   int i;  
};  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   Unsafe *pUnsafe = func();   // C4412  
   // pUnsafe->Test();  
  
   Safe *pSafe = func2();   // OK  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий пример является файл заголовка, который объявляет два типа. `Unsafe` Тип является небезопасным, поскольку она содержит функцию-член.  
  
```  
// C4412.h  
struct Unsafe {  
   // will be __clrcall if #included in pure compilation  
   // defaults to __cdecl in native or mixed mode compilation  
   virtual void Test(int * pi);  
  
   // try the following line instead  
   // virtual void __cdecl Test(int * pi);  
};  
  
struct Safe {  
   int i;  
};  
```  
  
## <a name="example"></a>Пример  
 В этом примере экспортирует функции, типы, определенные в файле заголовка.  
  
```  
// C4412_2.cpp  
// compile with: /LD  
#include "C4412.h"  
  
void Unsafe::Test(int * pi) {  
   *pi++;  
}  
  
__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }  
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }  
```  
  
## <a name="example"></a>Пример  
 Значение по умолчанию, соглашение о вызовах **/CLR: pure** отличается от собственной компиляции.  Когда включается C4412.h `Test` по умолчанию равно `__clrcall`. При компиляции и запуске этой программы (не используйте **/c**), будет вызвано исключение.  
  
 Следующий пример приводит к возникновению ошибки C4412.  
  
```  
// C4412_3.cpp  
// compile with: /W2 /clr:pure /c /link C4412_2.lib  
#pragma warning (default : 4412)  
#include "C4412.h"  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   int n = 7;  
   Unsafe *pUnsafe = func();   // C4412  
   pUnsafe->Test(&n);  
  
   Safe *pSafe = func2();   // OK  
}  
```
