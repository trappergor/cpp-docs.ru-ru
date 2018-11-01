---
title: Практическое руководство. Добавление машинной библиотеки DLL в глобальный кэш сборок
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
ms.openlocfilehash: 1b11ebfae704ca1529113a00b463df728c85fe60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641367"
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Практическое руководство. Добавление машинной библиотеки DLL в глобальный кэш сборок

Собственная библиотека DLL (не COM) можно поместить в глобальный кэш сборок.

## <a name="example"></a>Пример

**/ ASSEMBLYLINKRESOURCE** позволяет внедрять собственная библиотека DLL в сборке.

Дополнительные сведения см. в разделе [Параметр /ASSEMBLYLINKRESOURCE (компоновка с ресурсом .NET Framework)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).

```
/ASSEMBLYLINKRESOURCE:MyComponent.dll
```

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)