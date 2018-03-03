---
title: "Предупреждение средств компоновщика LNK4254 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e17bcd03f92114c1b7cd21e63220cf6372c17bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4254"></a>Предупреждение средств компоновщика LNK4254
раздел «раздел 1» (смещение) объединены в раздел «2» (смещение) с разными атрибутами  
  
 Содержимое одного раздела было выполнено слияние в другой, но — разные атрибуты из двух разделов. Программа может привести к непредвиденным результатам. Например данные, которые вы хотите прочитать только теперь возможно для записи раздела.  
  
 Для устранения ошибки LNK4254, изменить или удалить запрос на слияние.  
  
 При разработке для x86 машин и Windows CE целевых объектов (ARM, MIPS, SH4 и Thumb) с помощью Visual C++. CRT доступен только для чтения. Если код зависит от предыдущего поведения (. CRT имеют чтение и запись), может возникнуть непредсказуемое поведение.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [/ MERGE (Слияние разделов)](../../build/reference/merge-combine-sections.md)  
  
-   [comment (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK4254.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```