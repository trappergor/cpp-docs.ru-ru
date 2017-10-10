---
title: "Ошибка компилятора C2732 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2732
dev_langs:
- C++
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 38b364ac890118ce90164c3003a76e0d3c2e100d
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2732"></a>Ошибка компилятора C2732
спецификация компоновки противоречит более ранней спецификации function  
  
 Функция уже объявлена с другим описателем компоновки.  
  
 Эта ошибка может возникать при включении файлов с различными описателями компоновки.  
  
 Для устранения этой ошибки измените оператор `extern`, чтобы согласовать компоновки. В частности, не заключайте директивы `#include` в блоки `extern "C"`.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2732:  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```
