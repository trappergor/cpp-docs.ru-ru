---
title: Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода, с помощью PInvoke
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
ms.openlocfilehash: e51e094cc013250fc254a09e279745f1f9c108ac
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748545"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>Практическое руководство. Вызов неуправляемых библиотек DLL из управляемого кода, с помощью PInvoke

Функции, реализованные в неуправляемых библиотек DLL могут вызываться из управляемого кода с помощью функциональной возможности вызова неуправляемого кода (P/Invoke). Если исходный код для библиотеки DLL не доступен, P/Invoke является единственным для взаимодействия. Тем не менее в отличие от других языков .NET, Visual C++ предоставляет альтернативу P/Invoke. Дополнительные сведения см. в разделе [с помощью взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

## <a name="example"></a>Пример

В следующем примере кода используется Win32 [GetSystemMetrics](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics) функции для получения текущего разрешения экрана в пикселях.

Для функций, используйте только внутренние типы как аргументы и возвращаемые значения дополнительные действия не требуется. Другие типы данных, например указатели функций, массивы и структуры, требуются дополнительные атрибуты, чтобы обеспечить правильный маршалинг данных.

Несмотря на то, что это не обязательно, рекомендуется сделать объявления P/Invoke статические члены класса значений, чтобы они не существуют в глобальном пространстве имен, как показано в этом примере.

```
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

## <a name="see-also"></a>См. также

[Использование явного вызова Pinvoke в C++ (атрибут DllImport)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
