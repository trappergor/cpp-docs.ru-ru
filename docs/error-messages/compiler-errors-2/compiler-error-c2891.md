---
title: Ошибка компилятора C2891 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01741d1cc67f0045c46ab392212625b9e1a2d8ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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