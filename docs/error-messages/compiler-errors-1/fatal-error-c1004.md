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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 528147eceadd35cc0d9fe656bdc7ce7965339a0a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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