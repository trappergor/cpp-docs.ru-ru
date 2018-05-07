---
title: Неустранимая ошибка C1004 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d88f76c00c8f5b36acf238f0da88e908eac6dbe8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1004"></a>Неустранимая ошибка C1004
Непредвиденное обнаружение конца файла  
  
 Компилятор достиг конца исходного файла без разрешения конструктора. Код может отсутствовать один из следующих элементов:  
  
-   Закрывающей фигурной скобки  
  
-   Закрывающая скобка  
  
-   Закрывающая метка комментария (* /)  
  
-   Точка с запятой  
  
 Чтобы устранить эту ошибку, проверьте следующее:  
  
-   Диске по умолчанию имеет недостаточно места для временных файлов, которые требуется примерно вдвое больше места, что и исходный файл.  
  
-   `#if` , Результатом которого является значение false, отсутствует закрывающая директива `#endif` директивы.  
  
-   Исходный файл не заканчивается возврата каретки и перевода строки.  
  
 Следующий пример приводит к возникновению ошибки C1004:  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 Возможное решение  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```