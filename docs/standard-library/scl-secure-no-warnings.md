---
title: "_SCL_SECURE_NO_WARNINGS | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: e2f39c4f07235c75204a63e634053f887682337e
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS
Вызов любого из потенциально опасных методов в стандартной библиотеке C++ приведет к [предупреждению компилятора (уровень 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Чтобы отключить это предупреждение, определите в своем коде макрос **_SCL_SECURE_NO_WARNINGS**:  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## <a name="remarks"></a>Примечания  
 Другие способы отключения предупреждения C4996 перечислены ниже:  
  
-   Использование параметра компилятора [/D (определения препроцессора)](../build/reference/d-preprocessor-definitions.md):  
  
 ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
```  
  
-   Использование параметра компилятора [/w](../build/reference/compiler-option-warning-level.md):  
  
 ```  
    cl /wd4996 [other compiler options] myfile.cpp  
```  
  
-   Использование директивы [предупреждение #pragma](../preprocessor/warning.md):  
  
 ```  
 #pragma warning(disable:4996)  
```  
  
 Кроме того, можно вручную изменить уровень предупреждения C4996 с параметром компилятора **/w\<l>\<n>**. Например, чтобы задать для предупреждения C4996 уровень 4:  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 Дополнительные сведения см. в разделах [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (уровень предупреждений)](../build/reference/compiler-option-warning-level.md).  
  
## <a name="see-also"></a>См. также  
 [Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)


