---
title: "Ошибка компилятора C3171 | Microsoft Docs"
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
  - "C3171"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3171"
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3171
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"module": не удается указать другие атрибуты модуля в проекте  
  
 Атрибуты [module](../../windows/module-cpp.md) с различными списками параметров были найдены в двух файлах компиляции.  При компиляции может быть указан только один уникальный атрибут `module`.  
  
 Аналогичные атрибуты `module` могут быть указаны в нескольких файлах исходного кода.  
  
 Например, если найдены следующие атрибуты `module`:  
  
```  
// C3171.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];  
int main() {}  
```  
  
 И далее,  
  
```  
// C3171b.cpp  
// compile with: C3171.cpp  
// C3171 expected  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];  
```  
  
 компилятор формирует сообщение об ошибке C3171 \(запишите значения разных версий\).