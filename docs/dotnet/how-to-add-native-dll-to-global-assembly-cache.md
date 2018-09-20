---
title: 'Практическое: Добавление машинной библиотеки DLL в глобальный кэш сборок | Документация Майкрософт'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 74b24b96b28d8c5805a075a5ac1eee41173fc427
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432000"
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