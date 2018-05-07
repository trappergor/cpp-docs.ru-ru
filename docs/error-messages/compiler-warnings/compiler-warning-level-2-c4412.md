---
title: Предупреждение (уровень 2) C4412 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d186a237c7eb21cdcdc51a896d58d11bc19c5b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4412"></a>Предупреждение компилятора (уровень 2) C4412
«функция»: подпись функции содержит тип «тип»; Объекты C++ небезопасно передавать между чистый код и смешанного или машинного.  
  
 **/CLR: pure** рекомендуется использовать параметр компилятора в Visual Studio 2015. Если у вас есть код, который должен быть «чистые», рекомендуется переносить его в C#.  
  
 Компилятор обнаружил потенциально небезопасную ситуацию, которая может привести к ошибке времени выполнения: вызов выполняется из **/CLR: pure** компилируемого объекта функции, импортированной с помощью dllimport, а также подпись функции содержит тип unsafe . Тип является небезопасным, если он содержит функцию-член или член данных, небезопасным типом или косвенное обращение к нему.  
  
 Это является нарушением безопасности из-за различия в вызовах соглашения между чистого и машинного кода по умолчанию (или смешанного машинного и управляемого). При импорте (через `dllimport`) функция в **/CLR: pure** компилируемого объекта, убедитесь, что объявления каждого типа в сигнатуре идентичны в единицу компиляции, которая экспортирует функцию (проявляя особенно осторожным различия в неявные соглашения о вызовах.)  
  
 Виртуальная функция-член зачастую может привести к непредвиденным результатам.  Тем не менее чтобы обеспечить получение правильных результатов следует выполнить проверку даже невиртуальной функции. Если вы уверены, что вы получаете правильные результаты, можно игнорировать это предупреждение.  
  
  
 C4412 по умолчанию отключено. В разделе [компилятора предупреждения выключенные по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) и [dllexport, dllimport](../../cpp/dllexport-dllimport.md) для получения дополнительной информации.  
  
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
 Следующий пример является файлом заголовка, который объявляет два типа. `Unsafe` Тип является небезопасным, поскольку она содержит функцию-член.  
  
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
 Значение по умолчанию, соглашение о вызовах **/CLR: pure** компиляции отличается от собственной компиляции.  Когда включается C4412.h `Test` по умолчанию используется значение `__clrcall`. Если компиляция и выполнение этой программы (не используйте **/c**), будет вызвано исключение.  
  
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