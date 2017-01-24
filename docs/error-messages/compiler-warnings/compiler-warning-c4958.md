---
title: "Предупреждение компилятора C4958 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4958"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4958"
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4958
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"операция": арифметика указателей недоступна для проверки  
  
 Использование арифметики указателей создает непроверяемый образ.  
  
 Для получения дополнительной информации см. [Чистый и проверяемый код](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью директивы pragma [warning](../../preprocessor/warning.md) или параметра компилятора [\/wd](../../build/reference/compiler-option-warning-level.md).  
  
 В следующем примере возникает ошибка C4958:  
  
```  
// C4958.cpp // compile with: /clr:safe // #pragma warning( disable : 4958 ) using namespace System; int main( ) { Int32 arr[] = new Int32[10]; Int32* p = &arr[0]; p++;   // C4958 }  
```  
  
 Компилятор реализует операции с массивами с использованием арифметики указателей. Таким образом, собственные массивы не подлежат проверке; используйте вместо них массив CLR. Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).  
  
 В следующем примере возникает ошибка C4958:  
  
```  
// C4958b.cpp // compile with: /clr:safe // #pragma warning( disable : 4958 ) int main() { int array[5]; array[4] = 0;   // C4958 }  
```