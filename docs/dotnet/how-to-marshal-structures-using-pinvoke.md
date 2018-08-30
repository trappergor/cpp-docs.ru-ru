---
title: 'Практическое: маршалирование структур с помощью PInvoke | Документация Майкрософт'
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
ms.openlocfilehash: a26394a906f40d6dc194118bb312cfe1a0ce834e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219888"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>Практическое руководство. Маршалирование структур с помощью PInvoke
В этом документе объясняется, как неуправляемый код функции, которые принимают структуры стиля C может вызываться из управляемых функций, с помощью P/Invoke. Несмотря на то, что мы рекомендуем использовать возможности взаимодействия C++ вместо P/Invoke, так как P/Invoke предоставляет мало времени компиляции сведений об ошибках, не является строго типизированным и может быть утомительным, если неуправляемый интерфейс API входит в состав библиотеки DLL и исходный код не доступно, P/Invoke является единственным параметром. В противном случае ознакомьтесь со следующими документами:  
  
-   [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
  
-   [Практическое руководство. Маршалинг строк с помощью PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)
  
 По умолчанию неуправляемые и управляемые структуры располагаются по-разному в памяти, успешно передачи через границу управляемых и неуправляемых структур требуются дополнительные действия, чтобы сохранить целостность данных.  
  
 В этом документе описаны этапы, необходимые для определения управляемых эквивалентов для неуправляемых структур, а также как полученных структур могут передаваться с неуправляемыми функциями. В этом документе предполагается, что простой структуры — те, которые не содержат строки или указатели — используются. Сведения о взаимодействии преобразуемых см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md). P/Invoke не может быть непреобразуемые типы возвращаемого значения. Преобразуемые типы имеют одинаковое представление в управляемом и неуправляемом коде. Дополнительные сведения см. в разделе [непреобразуемые и преобразуемые типы](https://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3).  
  
 Маршалинг простых ли преобразуемые структуры через границы управляемого и неуправляемого сначала необходимо определить управляемые версии каждой неуправляемой структуры. Эти структуры могут иметь любые допустимые имена; не существует связи между машинным и управляемым версией две структуры, отличные от их макет данных. Поэтому крайне важно, что управляемой версии содержит поля, имеющие одинаковый размер и в том же порядке, как собственную версию. (Имеется механизм проверки версий управляемой и собственной структуры эквивалентны, поэтому несовместимости не станет очевидным до времени выполнения. Это программист должен убедиться, что две структуры имеют один и тот же макет данных.)  
  
 Так как иногда членов управляемых структур для повышения производительности, она необходима для использования <xref:System.Runtime.InteropServices.StructLayoutAttribute> атрибут, чтобы указать, что структура располагаются последовательно. Также рекомендуется явно задавать параметры, используемые в собственной структуре упаковки структуры. (Несмотря на то что по умолчанию Visual C++ использует структуру размером 8 байт, упаковке для обоих управляемого кода).  
  
1.  Затем используйте <xref:System.Runtime.InteropServices.DllImportAttribute> объявить точки входа, которые соответствуют все неуправляемые функции, которые принимают структуру, но используют на управляемую версию структуры в сигнатуры функций, которая является метод в том случае, если вы используете то же имя для обеих версий Структура.  
  
2.  Теперь управляемого кода можно передать на управляемую версию структуры в неуправляемые функции, как будто они являются управляемыми. Эти структуры могут передаваться по значению или по ссылке, как показано в следующем примере.  
  
## <a name="example"></a>Пример  
 Следующий код состоит из неуправляемый и управляемый модуль. Неуправляемый модуль представляет собой DLL, определяет структуру, называемую расположение и функция GetDistance, принимающая два экземпляра структуры Location. Второй модуль является управляемым приложением командной строки, импортирует функция GetDistance импортируется, но определяется с точки зрения управляемый эквивалент структуры расположения, MLocation. На практике же имя будет использоваться, возможно, для обеих версий структуры. Тем не менее другое имя здесь используется для демонстрации того, что прототип DllImport определяется на основе управляемой версии.  
  
 Обратите внимание, что часть библиотеки DLL предоставляется управляемого кода, с помощью стандартной #include. На самом деле библиотеки DLL осуществляется во время выполнения, поэтому проблемы с функциями, импортированные с помощью DllImport не обнаруживаются во время компиляции.  
  
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
