---
title: "Предупреждение компилятора C4335 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: dc8436664038d3f53f3a01d5006c41c3d0e4c8f0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-warning-c4335"></a>Предупреждение компилятора C4335
Обнаружен файл в формате Mac: преобразуйте исходный файл в формат DOS или UNIX  
  
 Символ окончания строки в первой строке исходного файла — Macintosh стиля («\r»), в отличие от UNIX («\n») или DOS («\r\n»).  
  
 Это предупреждение всегда выдается как ошибки.  В разделе [предупреждение](../../preprocessor/warning.md) Дополнительные сведения о том, как отключить это предупреждение.  Кроме того это предупреждение при компиляции выдается только один раз. Таким образом Если используется несколько `#include` директив, в которых файлы указываются в формате Macintosh, C4335 выдается всего один раз.  
  
 Чтобы создать файлы в формате Macintosh — с помощью **Дополнительные параметры сохранения** (на **файл** меню) в Visual Studio.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4335.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```
