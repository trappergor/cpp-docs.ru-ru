---
title: "Предупреждение компилятора (уровень 1) C4364 | Microsoft Docs"
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
  - "C4364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4364"
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#using для сборки "file" ранее увиденный в расположении \(line\_number\) без атрибута as\_friend; поскольку as\_friend не использовался  
  
 Директива `#using` была повторена для данного файла метаданных, но квалификатор `as_friend` не использовался в первом случае; компилятор отклонит второй `as_friend`.  
  
 Для получения дополнительной информации см. [Дружественные сборки \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md).  
  
## Пример  
 В следующем примере показано создание компонента.  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## Пример  
 В следующем примере формируется сообщение об ошибке С4364.  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```