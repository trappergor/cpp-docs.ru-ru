---
title: "Ошибка компилятора C2891 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6c35294472fe4142e7e6689adfc5f5f71c27b664
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2891"></a>Ошибка компилятора C2891
«параметр»: невозможно получить адрес параметра шаблона  
  
 Невозможно получить адрес параметра шаблона, если он не является ссылкой lvalue. Параметры типа не являются значениями, так как они имеют нет IP-адреса. Не являющиеся типом значения в списках параметров шаблона, которые не являются значениями также имеют адреса. Ниже приводится пример кода, вызывающего Ошибка компилятора C2891, так как значение передается в качестве параметра шаблона компилятором копию аргумента шаблона.  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 Параметры шаблона, которые являются значениями lvalue, такие как ссылочные типы, можно свой адрес предпринять.  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 Чтобы исправить эту ошибку, не принимают адрес параметра шаблона, если только это значение lvalue.
