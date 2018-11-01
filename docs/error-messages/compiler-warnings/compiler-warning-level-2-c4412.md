---
title: Предупреждение компилятора (уровень 2) C4412
ms.date: 11/04/2016
f1_keywords:
- C4412
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
ms.openlocfilehash: 2c9d50fc3433321c0ca92366a512892212545754
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665521"
---
# <a name="compiler-warning-level-2-c4412"></a>Предупреждение компилятора (уровень 2) C4412

> "*функция*": подпись функции содержит тип "*тип*"; Объекты C++ небезопасно передавать между кодом чистого и смешанного или собственного.

## <a name="remarks"></a>Примечания

**/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017. Если у вас есть код, который должен быть чистым, мы рекомендуем портировать его с C#.

Компилятор обнаружил потенциально небезопасных ситуацию, которая может привести к ошибке времени выполнения: вызов выполняется из **/CLR: pure** компилируемого объекта функции, импортированной с помощью dllimport и сигнатура функции содержит тип unsafe . Тип является небезопасным, если он содержит функцию-член или член данных, небезопасный тип или косвенное обращение к нему.

Это является небезопасным из-за различия в используемом по умолчанию, соглашения о вызовах между чистого и машинного кода (или смешанного машинного и управляемого кода). При импорте (через `dllimport`) функцию в **/CLR: pure** единице компиляции, убедитесь, что объявления каждого типа в сигнатуре идентичны в единицу компиляции, которая экспортирует функцию (Будьте особенно осторожны различия в неявные соглашения о вызовах.)

Виртуальная функция-член зачастую может привести к непредвиденным результатам.  Тем не менее даже Невиртуальная функция необходимо тестировать, чтобы обеспечить получение правильных результатов. Если вы уверены, что вы получаете правильные результаты, это предупреждение можно игнорировать.

C4412 по умолчанию отключены. См. в разделе [компилятора Warnings That Are Off по умолчанию](../../preprocessor/compiler-warnings-that-are-off-by-default.md) и [dllexport, dllimport](../../cpp/dllexport-dllimport.md) Дополнительные сведения.

Чтобы устранить это предупреждение, удалите все функции из типа.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4412.

```cpp
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

Следующий пример — это файл заголовка, который объявляет два типа. `Unsafe` Тип является небезопасным, так как она содержит функцию-член.

```cpp
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

```cpp
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

По умолчанию, соглашение о вызовах **/CLR: pure** компиляции отличается от собственной компиляции.  Если включен C4412.h, `Test` по умолчанию используется `__clrcall`. Если вы скомпилируете и запустите эту программу (не используйте **/c**), будет вызвано исключение.

Следующий пример приводит к возникновению ошибки C4412.

```cpp
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