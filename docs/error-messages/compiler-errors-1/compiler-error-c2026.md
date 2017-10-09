---
title: "Ошибка компилятора C2026 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 97937579c12730fecfa89c69d9e7cf51229b5c6c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2026"></a>Ошибка компилятора C2026
слишком большая строка, замыкающие знаки сокращены  
  
 Строка превысило ограничение 16380 однобайтовых знаков.  
  
 До, объединяемых смежные строки строка не может быть длиннее 16380 однобайтовых символов.  
  
 Строка Юникода вдвое Эта длина может также вызвать эту ошибку.  
  
 Если имеется строка, определяются следующим образом, возникает ошибка C2026:  
  
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
  
 Вы можете хранить чрезвычайно большого строковых литералов (32 КБ или больше) в настраиваемый ресурс или внешнего файла. В разделе [Создание нового настраиваемого ресурса или ресурса данных](../../windows/creating-a-new-custom-or-data-resource.md) для получения дополнительной информации.
