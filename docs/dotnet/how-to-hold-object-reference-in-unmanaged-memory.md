---
title: 'Практическое: хранение ссылки на объект в неуправляемой памяти | Документация Майкрософт'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3153a34844885e2b753bf68d74b7757c5d11fb1d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443466"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>Практическое руководство. Хранение ссылки на объект в неуправляемой памяти

Можно использовать gcroot.h, который служит оболочкой для <xref:System.Runtime.InteropServices.GCHandle>, для хранения ссылки на объект CLR в неуправляемой памяти. Кроме того, можно использовать `GCHandle` напрямую.

## <a name="example"></a>Пример

```
// hold_object_reference.cpp
// compile with: /clr
#include "gcroot.h"
using namespace System;

#pragma managed
class StringWrapper {

private:
   gcroot<String ^ > x;

public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      x = str;
   }

   void PrintString() {
      String ^ targetStr = x;
      Console::WriteLine("StringWrapper::x == {0}", targetStr);
   }
};
#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::x == ManagedString
```

## <a name="example"></a>Пример

`GCHandle` предоставляет возможность хранения ссылки на управляемый объект в неуправляемой памяти.  Использовании <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> метод для создания непрозрачный дескриптор для управляемого объекта и <xref:System.Runtime.InteropServices.GCHandle.Free%2A> для его освобождения. Кроме того <xref:System.Runtime.InteropServices.GCHandle.Target%2A> метод позволяет получить ссылку на объект обратно из дескриптора в управляемом коде.

```
// hold_object_reference_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed
class StringWrapper {
   IntPtr m_handle;
public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));
   }
   ~StringWrapper() {
      static_cast<GCHandle>(m_handle).Free();
   }

   void PrintString() {
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);
   }
};

#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::m_handle == ManagedString
```

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)