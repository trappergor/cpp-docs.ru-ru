---
title: 'Как: маршалирование структур с помощью PInvoke | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4ff1801c9bb2de06ae2717e8f69bcd39fdf3bc98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136617"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Практическое руководство. Маршалирование структур с помощью PInvoke
В этом документе объясняется, как собственных функций, принимающих структуры в стиле языка C может вызываться из управляемых функций, с помощью P/Invoke. Несмотря на то, что мы рекомендуем использовать возможности взаимодействия C++ вместо P/Invoke, так как P/Invoke предоставляет мало времени компиляции сведений об ошибках, не является строго типизированным и может быть сложно реализовать, если неуправляемый интерфейс API упакован как библиотека DLL и исходный код не доступно, P/Invoke является единственным параметром. В противном случае см. в следующих документах:  
  
-   [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
  
-   [Практическое руководство. Маршалинг строк с помощью PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)
  
 По умолчанию неуправляемые и управляемые структуры располагаются по-разному в памяти, успешно Передача структур через границы управляемого и неуправляемого требует дополнительных действий, чтобы сохранить целостность данных.  
  
 В этом документе описаны этапы, необходимые для определения управляемых эквивалентов для неуправляемых структур, а также как неуправляемые функции могут передаваться полученных структур. В этом документе предполагается, что простой структуры — те, которые не содержат строки или указатели — используются. Сведения о взаимодействии преобразуемых см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke не может быть непреобразуемые типы возвращаемого значения. Преобразуемые типы имеют одинаковое представление в управляемом и неуправляемом коде. Дополнительные сведения см. в разделе [преобразуемые и непреобразуемые не типы](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3).  
  
 Маршалинг простых ли преобразуемых структур через границы управляемого и неуправляемого сначала необходимо определить управляемые версии каждой неуправляемой структуры. Эти структуры могут иметь любые допустимые имена; Отсутствует связь между машинным и управляемым версией двух структур, отличные от их макет данных. Крайне важно, управляемую версию содержит поля, имеющие одинаковый размер и в том же порядке, как собственную версию. (Отсутствует механизм для обеспечения того, что управляемые и собственные версии структуры эквивалентны, несовместимости не станут очевидными до времени выполнения. Он является обязанностью программиста, убедитесь, что две структуры имеют один и тот же макет данных.)  
  
 Поскольку иногда членов управляемых структур для повышения производительности, бывает необходимо использовать <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут, чтобы указать, что структура порядок следования. Также рекомендуется явно задавать параметры быть таким же, как используется собственный структурой упаковки структуры. (Несмотря на то что по умолчанию Visual C++ используется 8-байтная упаковка как для управляемого кода структуры).  
  
1.  Затем используйте <xref:System.Runtime.InteropServices.DllImportAttribute> объявить точки входа, которые соответствуют все неуправляемые функции, которые принимают структуру, но использовать управляемую версию структуры сигнатур функций, которая является метод, при использовании того же имени для обеих версий Структура.  
  
2.  Теперь управляемого кода можно передать управляемую версию структуры неуправляемых функций, как будто они являются управляемыми. Эти структуры могут передаваться по значению или по ссылке, как показано в следующем примере.  
  
## <a name="example"></a>Пример  
 Следующий код состоит из неуправляемый и управляемый модуль. Неуправляемый модуль является библиотекой DLL, определяется структура Location и функция GetDistance, принимающая два экземпляра структуры Location. Второй модуль представляет собой управляемое приложение командной строки, которая импортирует функция GetDistance импортируется, но определяется с помощью управляемого эквивалента структуры Location MLocation. На практике тем же именем будут, скорее всего, использовать для обеих версий структуры. Однако другое имя здесь используется для демонстрации того, что прототип DllImport определен с помощью управляемой версии.  
  
 Обратите внимание, что никакие компоненты библиотеки DLL не предоставляются для управляемого кода, с помощью стандартной #include. На самом деле DLL осуществляется во время выполнения, поэтому проблемы с функциями, импортированные с помощью DllImport не обнаруживаются во время компиляции.  
  
```  
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
  
```  
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
  
## <a name="see-also"></a>См. также  
 [Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
