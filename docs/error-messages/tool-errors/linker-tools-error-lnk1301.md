---
title: "Ошибка средств компоновщика LNK1301 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1301
dev_langs:
- C++
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3694841447a83f02821aa260cdfdceaf7bd2ec5b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1301"></a>Ошибка средств компоновщика LNK1301
Модули среды clr LTCG найден, несовместимые с /LTCG:parameter  
  
 Модуле, скомпилированном с параметром/CLR и/GL передан компоновщику вместе с профильной оптимизации (PGO) параметров/LTCG.  
  
 Профильной оптимизации для модулей/CLR не поддерживаются.  
  
 Дополнительные сведения:  
  
-   [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md)  
  
-   [/ Параметр LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)  
  
-   [/ CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Не компилировать с параметром/CLR или не связана с одним из параметров профильной Оптимизации/LTCG.  
  
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
