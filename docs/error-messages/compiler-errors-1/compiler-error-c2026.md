---
title: "Ошибка компилятора C2026 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
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
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: c429f81c64b7710b7edc2b8540d98e8c790e4062
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2026"></a>Ошибка компилятора C2026
слишком большая строка, замыкающие знаки сокращены  
  
 Строка была превышает ограничение в 16380 однобайтовых знаков.  
  
 До, объединяемых смежные строки строка не может превышать 16380 однобайтовых знаков.  
  
 Эта ошибка также возникает при вдвое этой длины строки в Юникоде.  
  
 Если строка, определяются следующим образом, возникает ошибка C2026:  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Можно разбить строку следующим образом:  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Вы можете хранить чрезвычайно большого строковых литералов (32 КБ или больше) на настраиваемого ресурса или внешнего файла. В разделе [Создание нового настраиваемого ресурса или ресурса данных](../../windows/creating-a-new-custom-or-data-resource.md) для получения дополнительной информации.
