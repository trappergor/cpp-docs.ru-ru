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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: acee7db1513dd3e999a90218ea674930c2a13f1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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