---
title: Предупреждение средств компоновщика LNK4254 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb57882ab4269c06a53ed73fed2a9d6caf2f2c85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4254"></a>Предупреждение средств компоновщика LNK4254
раздел «раздел 1» (смещение) объединены в раздел «2» (смещение) с разными атрибутами  
  
 Содержимое одного раздела было выполнено слияние в другой, но — разные атрибуты из двух разделов. Программа может привести к непредвиденным результатам. Например данные, которые вы хотите прочитать только теперь возможно для записи раздела.  
  
 Для устранения ошибки LNK4254, изменить или удалить запрос на слияние.  
  
 При разработке для x86 машин и Windows CE целевых объектов (ARM, MIPS, SH4 и Thumb) с помощью Visual C++. CRT доступен только для чтения. Если код зависит от предыдущего поведения (. CRT имеют чтение и запись), может возникнуть непредсказуемое поведение.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [/MERGE (слияние разделов)](../../build/reference/merge-combine-sections.md)  
  
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