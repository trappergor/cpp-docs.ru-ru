---
title: Двойные преобразования (C++) | Документация Майкрософт
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
ms.openlocfilehash: f1ee67c41fde7b380c58d479764e6e212274cf41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421340"
---
# <a name="double-thunking-c"></a>Двойное преобразование (С++)

Двойное преобразование относится к потере производительности, которые могут возникнуть при вызов функции в управляемом контексте вызывает управляемую функцию Visual C++ и когда выполнение программы вызывает функции основную точку входа, чтобы вызвать управляемую функцию. В этом разделе рассматриваются возникновения двойного и как можно избежать снижения производительности.

## <a name="remarks"></a>Примечания

По умолчанию при компиляции с параметром **/CLR**, определение управляемой функции заставляет компилятор создавать управляемую точку входа и машинную точку входа. Это позволяет управляемую функцию для вызова из мест вызова машинного и управляемого кода. Тем не менее если существует основную точку входа, может быть точкой входа для всех вызовов функции. Если вызывающей функции является управляемым, машинной точки входа, затем вызовет управляемую точку входа. По сути, требуется два вызова для вызова функции (таким образом, двойные преобразования). Например виртуальные функции всегда вызываются через основную точку входа.

Одно решение заключается в сообщить компилятору не создавать основную точку входа для управляемой функции, что функция будет вызываться только из управляемого контекста с помощью [__clrcall](../cpp/clrcall.md) соглашение о вызовах.

Аналогично Если вы экспортируете ([dllexport, dllimport](../cpp/dllexport-dllimport.md)) управляемой функции, основную точку входа, и любая функция, которая импортирует и вызывает эту функцию будет вызываться через машинную точку входа. Чтобы избежать двойного в этой ситуации, следует использовать семантику собственного экспорта и импорта; просто ссылаться на метаданные с помощью `#using` (см. в разделе [# директива using](../preprocessor/hash-using-directive-cpp.md)).

Компилятор был обновлен на сокращение ненужных двойного. Например, любая функция с управляемым типом в сигнатуре (включая возвращаемый тип) будет неявно иметь пометку `__clrcall`. Дополнительные сведения о исключения двойного преобразования, см. в разделе [ https://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx ](https://msdn.microsoft.com/msdnmag/issues/05/01/COptimizations/default.aspx).

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем образце показано двойное преобразование. При компиляции в машинный код (без **/CLR**), вызов виртуальной функции в `main` создает один вызов `T`скопируйте конструктор и один вызов деструктора. Аналогичное поведение наблюдается, когда виртуальная функция объявляется с **/CLR** и `__clrcall`. Тем не менее если только что скомпилированные с помощью **/CLR**, вызов функции создает вызов конструктора копии, но имеется еще один вызов конструктора копии из-за машинные управляемые преобразователь.

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

Приведенный выше образец было показано создание двойное преобразование. В этом примере показан результат. `for` Цикл вызывает виртуальную функцию и программа сообщает время выполнения. Максимальное время передается в том случае, если программа скомпилирована с **/CLR**. Минимальное время включаются в отчеты при компиляции без **/CLR** или если виртуальная функция объявлена с `__clrcall`.

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