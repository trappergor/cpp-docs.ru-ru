---
title: "Предупреждение компилятора C4335 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4335
dev_langs: C++
helpviewer_keywords: C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea0a981c00a1941c3004ac820edbcbbbf0776c4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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