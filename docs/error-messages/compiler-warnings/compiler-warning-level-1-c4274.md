---
title: "Компилятор C4274 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: fbba1e6dde180e77afe7ed8960849ee8cc0fd108
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4274"></a>Компилятор C4274 предупреждение (уровень 1)
\#Идентификатор — игнорировать; в документации #pragma comment (exestr, 'строка')  
  
 `#ident` Директива, которая вставляет пользовательской строки в объект или исполняемый файл, является устаревшей. Следовательно компилятор игнорирует директивы.  
  
> [!CAUTION]
>  C4274 предупреждение о необходимости использовать [#pragma comment (exestr, 'строка')](../../preprocessor/comment-c-cpp.md) директивы. Тем не менее это является устаревшим и будет изменен в будущих версиях компилятора. Если вы используете `#pragma` директив, компоновщик (LINK.exe) пропускает запись комментария, созданную директивой и выдает предупреждение [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Вместо `#ident` директив, мы рекомендуем использовать строку ресурса версии файла в приложении.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалить `#ident "` *строка* `"` директивы.  
  
## <a name="see-also"></a>См. также  
 [комментарий (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [Предупреждение средств компоновщика LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Работа с файлами ресурсов](../../windows/working-with-resource-files.md)
