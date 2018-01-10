---
title: "Предупреждение средств компоновщика LNK4253 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4253
dev_langs: C++
helpviewer_keywords: LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d1142544852980b8bd1d543783a9ffdf3361879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4253"></a>Предупреждение средств компоновщика LNK4253
раздел «раздел 1», не объединены в раздел «2»; Слияние «section3»  
  
 Компоновщик обнаружил несколько конфликтующих запросов объединения. Компоновщик будет игнорировать один из запросов.  
  
 Объект **/MERGE** параметр или директива и `from` раздел уже был объединен в другой раздел из-за предыдущего **/MERGE** параметре или директиве (или в результате явного объединения Компоновщик).  
  
 Чтобы устранить LNK4253, удалите один из запросов объединения.  
  
 При разработке для x86 машин и Windows CE целевых объектов (ARM, MIPS, SH4 и Thumb) с помощью Visual C++. Раздел CRT теперь только для чтения. Если код зависит от предыдущего поведения (. CRT имеют чтение и запись), может возникнуть непредсказуемое поведение.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [/ MERGE (Слияние разделов)](../../build/reference/merge-combine-sections.md)  
  
-   [comment (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>Пример  
 В следующем примере компоновщик для слияния `.rdata` статьи дважды, но в разные разделы. Следующий пример приводит к возникновению ошибки LNK4253.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```