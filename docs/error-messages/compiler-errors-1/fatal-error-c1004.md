---
title: "Неустранимая ошибка C1004 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6a9e74d7918e1cb2c9190c87f4f1ec75f89237b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
  
 Возможное решение:  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```
