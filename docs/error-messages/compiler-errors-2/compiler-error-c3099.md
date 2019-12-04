---
title: Ошибка компилятора C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: 81f508c47c678d86f8f95303861b42f8a70daa57
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750056"
---
# <a name="compiler-error-c3099"></a>Ошибка компилятора C3099

keyword: используйте [System::AttributeUsageAttribute] для управляемых атрибутов; используйте [Windows::Foundation::Metadata::AttributeUsageAttribute] для атрибутов WinRT

Для объявления атрибутов **/CLR** используйте <xref:System.AttributeUsageAttribute>. Используйте `Windows::Foundation::Metadata::AttributeUsageAttribute` для объявления атрибутов среды выполнения Windows.

Дополнительные сведения об атрибутах/CLR см. в разделе [определяемые пользователем атрибуты](../../extensions/user-defined-attributes-cpp-component-extensions.md). Поддерживаемые атрибуты в среда выполнения Windows см. в разделе [пространство имен Windows. Foundation. Metadata.](/uwp/api/windows.foundation.metadata)

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C3099 и приводятся сведения по ее устранению.

```cpp
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```
