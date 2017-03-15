---
title: "Ошибка компилятора C3170 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3170"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3170"
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3170
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

в проекте не допускается существование различающихся идентификаторов модуля  
  
 В двух файлах при компиляции были обнаружены атрибуты [module](../../windows/module-cpp.md) с разными именами.  При компиляции может быть указан только один уникальный атрибут `module`.  
  
 Аналогичные атрибуты `module` могут быть указаны в нескольких файлах исходного кода.  
  
 Например, при обнаружении следующих атрибутов module:  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 И далее,  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 Компилятор выдаст ошибку C3170 \(обратите внимание, что имена различаются\).