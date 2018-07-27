---
title: Создание типа Double (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 47d5bbbecc8e1b9743c543a503df1a0afa0dc0ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111212"
---
# <a name="double-thunking-c"></a>Двойное преобразование (С++)
Двойное преобразование относится к потере производительности, которые могут возникнуть при вызове функции в управляемом контексте вызывает управляемую функцию Visual C++ и когда выполнение программы вызывает функции машинную точку входа, чтобы вызвать управляемую функцию. В этом разделе рассматриваются возникновения двойного и как можно избежать снижения производительности.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию при компиляции с параметром **/CLR**, определение управляемой функции заставляет компилятор создавать управляемую точку входа и машинную точку входа. Это позволяет управляемая функция должна вызываться из мест вызова машинного и управляемого. Тем не менее если существует машинную точку входа, может быть точка входа для всех вызовов функции. Если вызывающая функция является управляемым, основную точку входа, вызовет управляемую точку входа. Фактически для вызова функции требуется два вызова (следовательно, две преобразования). Например виртуальные функции всегда вызываются через машинную точку входа.  
  
 Одно решение заключается в сообщении компилятору не создавать машинную точку входа для управляемой функции, и вызывать функцию из управляемого контекста с помощью [__clrcall](../cpp/clrcall.md) соглашение о вызовах.  
  
 Аналогично Если вы экспортируете ([dllexport, dllimport](../cpp/dllexport-dllimport.md)) управляемой функции, основную точку входа, и любая функция, которая импортирует и вызывает данную функцию будет вызываться через машинную точку входа. Чтобы избежать двойного в такой ситуации, следует использовать семантику собственного экспорта и импорта; просто создайте ссылку на метаданные через `#using` (см. [# директива using](../preprocessor/hash-using-directive-cpp.md)).  
  
 Компилятор теперь сокращение нежелательного двойного. Например, любая функция с управляемым типом в сигнатуре (включая возвращаемый тип) будет явно помечена как `__clrcall`. Дополнительные сведения о двойного преобразования исключения в разделе [ http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx ](http://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем образце показано двойное преобразование. При компиляции в машинный код (без **/CLR**), вызов виртуальной функции в `main` создает один вызов `T`элемента конструктора копирования и один вызов деструктора. Похожее поведение наблюдается, когда виртуальная функция объявлена с **/CLR** и `__clrcall`. Тем не менее при компиляции только с **/CLR**, вызов функции создает вызов конструктора копирования, но имеется другой вызов конструктора копирования из-за машинного управляемому преобразованию.  
  
### <a name="code"></a>Код  
  
```  
// double_thunking.cpp  
// compile with: /clr  
#include <stdio.h>  
struct T {  
   T() {  
      puts(__FUNCSIG__);  
   }  
  
   T(const T&) {  
      puts(__FUNCSIG__);  
   }  
  
   ~T() {  
      puts(__FUNCSIG__);  
   }  
  
   T& operator=(const T&) {  
      puts(__FUNCSIG__);  
      return *this;  
   }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
  
   printf("calling struct S\n");  
   pS->f(t);  
   printf("after calling struct S\n");  
}  
```  
  
### <a name="sample-output"></a>Пример результатов выполнения  
  
```  
__thiscall T::T(void)  
calling struct S  
__thiscall T::T(const struct T &)  
__thiscall T::T(const struct T &)  
__thiscall T::~T(void)  
__thiscall T::~T(void)  
after calling struct S  
__thiscall T::~T(void)  
```  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Приведенный выше образец было показано создание двойное преобразование. В этом примере показан результат. `for` Цикл вызывает виртуальную функцию и программа сообщает время выполнения. Максимальное время, отображается при компиляции программы с **/CLR**. Минимальное время выводятся при компиляции без **/CLR** или если виртуальная функция объявлена с `__clrcall`.  
  
### <a name="code"></a>Код  
  
```  
// double_thunking_2.cpp  
// compile with: /clr  
#include <time.h>  
#include <stdio.h>   
  
#pragma unmanaged  
struct T {  
   T() {}  
   T(const T&) {}  
   ~T() {}  
   T& operator=(const T&) { return *this; }  
};  
  
struct S {  
   virtual void /* __clrcall */ f(T t) {};  
} s;  
  
int main() {  
   S* pS = &s;  
   T t;  
   clock_t start, finish;  
   double  duration;  
   start = clock();  
  
   for ( int i = 0 ; i < 1000000 ; i++ )  
      pS->f(t);  
  
   finish = clock();  
   duration = (double)(finish - start) / (CLOCKS_PER_SEC);  
   printf( "%2.1f seconds\n", duration );  
   printf("after calling struct S\n");  
}  
```  
  
### <a name="sample-output"></a>Пример результатов выполнения  
  
```  
4.2 seconds  
after calling struct S  
```  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)