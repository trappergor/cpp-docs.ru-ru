---
title: Практическое руководство. Маршалирование структур с помощью PInvoke
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
ms.openlocfilehash: fe5d2cf4804baea286827e9d5e270c10cd587b30
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545201"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Практическое руководство. Маршалирование структур с помощью PInvoke

В этом документе объясняется, как в управляемых функциях с помощью P/Invoke можно вызывать собственные функции, которые принимают структуры в стиле C. Хотя мы рекомендуем использовать функции C++ взаимодействия вместо p/Invoke, поскольку p/Invoke предоставляет небольшие отчеты об ошибках во время компиляции, не является типобезопасным и может быть утомительным для реализации, если неуправляемый API упакован в виде библиотеки DLL и исходный код недоступен, то единственным вариантом является P/Invoke. В противном случае см. следующие документы:

- [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [Практическое руководство. Маршалинг строк с помощью PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)

По умолчанию машинные и управляемые структуры в памяти размещаются по-разному, поэтому для успешной передачи структур по управляемой и неуправляемой границам требуются дополнительные действия для сохранения целостности данных.

В этом документе объясняются шаги, необходимые для определения управляемых эквивалентов машинных структур и того, как полученные структуры можно передавать в неуправляемые функции. В этом документе предполагается, что используются простые структуры (те, которые не содержат строк или указатели). Сведения о непреобразуемой взаимодействии см. [в разделе C++ использование взаимодействия (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke не может иметь непреобразуемые типы в качестве возвращаемого значения. Преобразуемые типы имеют одинаковое представление в управляемом и неуправляемом коде. Дополнительные сведения см. в разделе непреобразуемые и преобразуемые [типы](/dotnet/framework/interop/blittable-and-non-blittable-types).

Для упаковки простых непреобразуемых структур в управляемой и неуправляемой границах сначала необходимо определить управляемые версии каждой собственной структуры. Эти структуры могут иметь любое допустимое имя. нет связи между собственной и управляемой версиями двух структур, кроме структуры данных. Поэтому крайне важно, чтобы управляемая версия содержала поля, имеющие одинаковый размер и в том же порядке, что и собственная версия. (Не существует механизма обеспечения эквивалентности управляемых и собственных версий структуры, поэтому несовместимость не будет очевидна до времени выполнения. Программист следит за тем, чтобы две структуры имели одинаковый макет данных.)

Поскольку элементы управляемых структур иногда переупорядочиваются в целях повышения производительности, необходимо использовать атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>, чтобы указать, что структура размещается последовательно. Также рекомендуется явно задать параметр упаковки структуры так же, как он используется в собственной структуре. (Хотя по умолчанию визуальный C++ элемент использует 8-байтовую структуру для управляемого кода.)

1. Затем используйте <xref:System.Runtime.InteropServices.DllImportAttribute> для объявления точек входа, соответствующих неуправляемым функциям, которые принимают структуру, но используйте управляемую версию структуры в сигнатурах функций, которая является затеи точкой, если для обеих версий структуры используется одно и то же имя.

1. Теперь управляемый код может передавать управляемую версию структуры неуправляемым функциям, как будто они фактически являются управляемыми функциями. Эти структуры могут передаваться либо по значению, либо по ссылке, как показано в следующем примере.

## <a name="example"></a>Пример

Следующий код состоит из неуправляемого и управляемого модуля. Неуправляемый модуль — это библиотека DLL, которая определяет структуру с именем Location и функцию, именуемую Distance, которая принимает два экземпляра структуры расположения. Второй модуль — это управляемое приложение командной строки, которое импортирует функцию Distance, но определяет ее с точки зрения управляемого эквивалента структуры Location, Млокатион. На практике такое же имя может использоваться для обеих версий структуры. Однако здесь используется другое имя, чтобы продемонстрировать, что прототип DllImport определен в терминах управляемой версии.

Обратите внимание, что ни одна часть библиотеки DLL не предоставляется управляемому коду с помощью традиционной директивы #include. На самом деле библиотека DLL доступна только во время выполнения, поэтому проблемы с функциями, импортированными с помощью DllImport, не обнаруживаются во время компиляции.

```cpp
// TraditionalDll3.cpp
// compile with: /LD /EHsc
#include <iostream>
#include <stdio.h>
#include <math.h>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
   #define TRADITIONALDLL_API __declspec(dllexport)
#else
   #define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct Location {
   int x;
   int y;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API double GetDistance(Location, Location);
   TRADITIONALDLL_API void InitLocation(Location*);
}

double GetDistance(Location loc1, Location loc2) {
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   printf_s("[unmanaged] Initializing location...\n");
   lp->x = 50;
   lp->y = 50;
}
```

## <a name="example"></a>Пример

```cpp
// MarshalStruct_pi.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MLocation {
   int x;
   int y;
};

value struct TraditionalDLL {
   [DllImport("TraditionalDLL3.dll")]
   static public double GetDistance(MLocation, MLocation);
   [DllImport("TraditionalDLL3.dll")]
   static public double InitLocation(MLocation*);
};

int main() {
   MLocation loc1;
   loc1.x = 0;
   loc1.y = 0;

   MLocation loc2;
   loc2.x = 100;
   loc2.y = 100;

   double dist = TraditionalDLL::GetDistance(loc1, loc2);
   Console::WriteLine("[managed] distance = {0}", dist);

   MLocation loc3;
   TraditionalDLL::InitLocation(&loc3);
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);
}
```

```Output
[unmanaged] loc1(0,0) loc2(100,100)
[managed] distance = 141.42135623731
[unmanaged] Initializing location...
[managed] x=50 y=50
```

## <a name="see-also"></a>См. также:

[Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
