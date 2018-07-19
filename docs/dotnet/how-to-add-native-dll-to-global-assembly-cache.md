---
title: 'Как: Добавление машинной библиотеки DLL в глобальный кэш сборок | Документы Microsoft'
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
ms.openlocfilehash: b7363de172eabc664bcde1e3bf42f8cc499e4251
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129542"
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