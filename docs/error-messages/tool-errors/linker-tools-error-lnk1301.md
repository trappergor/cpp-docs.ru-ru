---
title: Ошибка средств компоновщика LNK1301 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b4e298ad3815c741ff6c901ac39bf7838ed135d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1301"></a>Ошибка средств компоновщика LNK1301
Найти, несовместимые с /LTCG:parameter модули среды LTCG clr  
  
 Модуле, скомпилированном с параметром/CLR и /GL был передан компоновщику вместе с профильной оптимизации (PGO) параметров/LTCG.  
  
 Профильной оптимизации для модулей, / CLR не поддерживаются.  
  
 Дополнительные сведения:  
  
-   [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/LTCG (создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не компилировать с параметром/CLR или не создавать связь с одним из параметров профильной Оптимизации/LTCG.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка LNK1301:  
  
```  
// LNK1301.cpp  
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj  
// LNK1301 expected  
class MyClass {  
public:  
   int i;  
};  
```