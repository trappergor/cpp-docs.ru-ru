---
title: Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
ms.openlocfilehash: 1eb5d5669c49dd49a411c275f8845dbbab989df3
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545093"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода с помощью PInvoke

Функции, реализованные в неуправляемых библиотеках DLL, могут вызываться из управляемого кода с помощью функции вызова неуправляемой платформы (P/Invoke). Если исходный код библиотеки DLL недоступен, вызов P/Invoke является единственным вариантом взаимодействия. Однако в отличие от других языков .NET, Visual C++ предоставляет альтернативу P/Invoke. Дополнительные сведения см. [в разделе C++ использование взаимодействия (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="example"></a>Пример

В следующем примере кода функция Win32 [жетсистемметрикс](/windows/win32/api/winuser/nf-winuser-getsystemmetrics) используется для получения текущего разрешения экрана в пикселях.

Для функций, использующих только внутренние типы в качестве аргументов и возвращаемых значений, дополнительная работа не требуется. Другие типы данных, такие как указатели на функции, массивы и структуры, занимают дополнительные атрибуты для обеспечения надлежащего маршалирования данных.

Хотя это не является обязательным, рекомендуется делать объявления P/Invoke статическими членами класса значений, чтобы они не существовали в глобальном пространстве имен, как показано в этом примере.

```cpp
// pinvoke_basic.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value class Win32 {
public:
   [DllImport("User32.dll")]
   static int GetSystemMetrics(int);

   enum class SystemMetricIndex {
      // Same values as those defined in winuser.h.
      SM_CXSCREEN = 0,
      SM_CYSCREEN = 1
   };
};

int main() {
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);
}
```

## <a name="see-also"></a>См. также:

[Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
