---
title: "Предупреждение компилятора C4394 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4394"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4394"
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4394
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": символ для каждого домена приложений не следует помечать с помощью \_\_declspec\(dllexport\)  
  
 Функция, помеченная модификатором [appdomain](../Topic/appdomain.md) `__declspec`, компилируется в код MSIL \(не в машинный код\), и экспортные таблицы \(модификатор [export](../../windows/export.md) `__declspec`\) не поддерживаются для управляемых функций.  
  
 Можно объявить управляемую функцию, чтобы иметь общую специальных возможностей.  Дополнительные сведения см. в разделах [Видимость типа](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [Видимость члена](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).  
  
 Предупреждение C4394 всегда выводится в качестве ошибки.  Возможно отключение этого предупреждения с помощью прагма\-директивы `#pragma warning` или параметра **\/wd**; дополнительные сведения см. в разделе [warning](../../preprocessor/warning.md) или [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(уровень предупреждений\)](../../build/reference/compiler-option-warning-level.md).  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C4394.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```