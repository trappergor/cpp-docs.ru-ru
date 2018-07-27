---
title: Предупреждение средств компоновщика LNK4253 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae4e88e1fe1434cd638d5c31cc8fd4d5c02c4de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301285"
---
# <a name="linker-tools-warning-lnk4253"></a>Предупреждение средств компоновщика LNK4253
раздел «раздел 1», не объединены в раздел «2»; Слияние «section3»  
  
 Компоновщик обнаружил несколько конфликтующих запросов объединения. Компоновщик будет игнорировать один из запросов.  
  
 Объект **/MERGE** параметр или директива и `from` раздел уже был объединен в другой раздел из-за предыдущего **/MERGE** параметре или директиве (или в результате явного объединения Компоновщик).  
  
 Чтобы устранить LNK4253, удалите один из запросов объединения.  
  
 При разработке для x86 машин и Windows CE целевых объектов (ARM, MIPS, SH4 и Thumb) с помощью Visual C++. Раздел CRT теперь только для чтения. Если код зависит от предыдущего поведения (. CRT имеют чтение и запись), может возникнуть непредсказуемое поведение.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [/MERGE (слияние разделов)](../../build/reference/merge-combine-sections.md)  
  
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