---
title: "Как: Добавление машинной библиотеки DLL в глобальный кэш сборок | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], native
- GAC (global assembly cache), loading native DLLs
- native DLLs [C++]
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: be55fd47cd6024d0660ed0c3e4594c9430f80cc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-native-dll-to-global-assembly-cache"></a>Практическое руководство. Добавление машинной библиотеки DLL в глобальный кэш сборок
Собственной библиотеки DLL (не COM), который можно поместить в глобальный кэш сборок.  
  
## <a name="example"></a>Пример  
 **/ Параметр ASSEMBLYLINKRESOURCE** позволяет внедрять собственной библиотеки DLL в сборке.  
  
 Дополнительные сведения см. в разделе [Параметр /ASSEMBLYLINKRESOURCE (компоновка с ресурсом .NET Framework)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## <a name="see-also"></a>См. также  
 [Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)