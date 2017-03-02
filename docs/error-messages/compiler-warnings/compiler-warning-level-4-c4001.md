---
title: "Предупреждение (уровень 4) C4001 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bbcf2db5f6650bd9118b28c8bbfe921d13306410
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4001"></a>Предупреждение (уровень 4) C4001 компилятора
использование нестандартного расширения для однострочного комментария  
  
 Однострочные комментарии являются стандартными в C++ и нестандартными в C. В строгом режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), файлы C, содержащие однострочные комментарии, создают ошибку C4001 из-за использования нестандартного расширения. Поскольку однострочные комментарии являются стандартными в C++, файлы C, содержащие однострочные комментарии, не создают ошибку C4001, при компиляции с помощью расширений Microsoft (/Ze).  
  
## <a name="example"></a>Пример  
 Чтобы отключить предупреждение, раскомментируйте [#pragma warning(disable:4001)](../../preprocessor/warning.md).  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```
