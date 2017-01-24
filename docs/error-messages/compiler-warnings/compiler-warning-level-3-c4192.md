---
title: "Предупреждение компилятора (уровень 3) C4192 | Microsoft Docs"
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
  - "C4192"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4192"
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4192
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

автоматически исключается 'name' при импорте библиотеки типов 'library'  
  
 В библиотеке `#import` содержится элемент, *name*, также определенный в системных заголовках Win32.  Из\-за ограничений библиотек типов, такие имена, как **IUnknown** или GUID часто определяются в библиотеках типов, что дублирует определения в системных заголовках.  Директива `#import` обнаружит эти элементы и не будет встраивать их в TLH\-файлы и TLI\-файлы.  
  
 Чтобы переопределить такой алгоритм действий, следует использовать атрибуты `#import`:[no\_auto\_exclude](../../preprocessor/no-auto-exclude.md) и [include\(\)](../../preprocessor/include-parens.md).