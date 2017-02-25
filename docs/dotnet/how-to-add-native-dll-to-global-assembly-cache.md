---
title: "Практическое руководство. Добавление машинной библиотеки DLL в глобальный кэш сборок | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL-библиотеки [C++], в машинном коде"
  - "GAC - глобальный кэш сборок, загрузка собственных библиотек DLL"
  - "собственные библиотеки DLL [C++]"
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Практическое руководство. Добавление машинной библиотеки DLL в глобальный кэш сборок
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Машинную библиотеку DLL, не являющуюся библиотекой COM, можно поместить в глобальный кэш сборок.  
  
## Пример  
 Параметр компоновщика **\/ASSEMBLYLINKRESOURCE** позволяет встроить машинную библиотеку DLL в сборку.  
  
 Для получения дополнительной информации см. [Параметр \/ASSEMBLYLINKRESOURCE \(ссылка на ресурс .NET Framework\)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md).  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)