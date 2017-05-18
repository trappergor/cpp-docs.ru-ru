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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 629d1c0b98f1bf6a813bd28f25c4e5afc0e7b367
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2891"></a>Ошибка компилятора C2891
«параметр»: невозможно получить адрес параметра шаблона  
  
 Невозможно получить адрес параметра шаблона, если он не является значением lvalue. Параметры типа не являются значениями, поскольку отсутствует адрес. Не являющиеся типом значения в списках параметров шаблона, которые не являются значениями также не имеют адреса. Это пример кода, который приводит к ошибке компилятора C2891, поскольку значение передается как параметр шаблона является копией аргумента шаблона компилятором.  
  
```  
template <int i> int* f() { return &i; }  
```  
  
 Параметры шаблона, которые являются значениями lvalue, такие как ссылочные типы, может адрес берется.  
  
```  
template <int& r> int* f() { return &r; }  
```  
  
 Чтобы исправить эту ошибку, не взять адрес параметра шаблона без lvalue.
