---
title: Ошибка компилятора C3854 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3854
dev_langs:
- C++
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbaed18984dbcc06b976a367ef9911528792ce52
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275516"
---
# <a name="compiler-error-c3854"></a>Ошибка компилятора C3854
выражение слева от «=» сводится к функции. Не удается назначить функцию (функция не является l значение)  
  
 Ссылка не может быть инициализирована повторно. Разыменование ссылки на функцию дает функцию, которая представляет собой rvalue, к которому невозможно присвоить. Таким образом нельзя назначить через ссылку на функцию.  
  
 Следующий пример приводит к возникновению ошибки C3854:  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```