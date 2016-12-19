---
title: "Ошибка компилятора C3172 | Microsoft Docs"
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
  - "C3172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3172"
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"module\_name": не удается указать другие атрибуты idl\_module в проекте  
  
 Атрибуты [idl\_module](../../windows/idl-module.md) с одинаковыми именами, но с разными параметрами — `dllname` или `version` — были найдены в двух файлах компиляции.  Для каждой компиляции может быть указан только один уникальный атрибут `idl_module`.  
  
 Аналогичные атрибуты `idl_module` могут быть указаны в нескольких файлах исходного кода.  
  
 Например, если найдены следующие атрибуты `idl_module`:  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 И далее,  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 компилятор формирует сообщение об ошибке C3172 \(запишите значения разных версий\).