---
title: Предупреждение компилятора C4335 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adb8a7b484ce0946f385c3b2a8669ba1b5ccf0d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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