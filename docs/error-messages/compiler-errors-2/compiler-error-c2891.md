---
title: "Ошибка компилятора C2891 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2891
dev_langs: C++
helpviewer_keywords: C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 979d77ad5b5bd0b68dd539695d6cb1b60b099c55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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