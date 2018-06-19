---
title: Предупреждение (уровень 1) C4274 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b941fc0cb32e268e33d3b0e1ae66079e8decaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33286150"
---
# <a name="compiler-warning-level-1-c4274"></a>Компилятор C4274 предупреждение (уровень 1)
\#Идентификатор — игнорируется; см. документацию для #pragma comment (exestr, "string")  
  
 `#ident` Директива, которая вставляет пользовательской строки в объект или исполняемый файл, является устаревшей. Как следствие компилятор игнорирует директиву.  
  
> [!CAUTION]
>  C4274 предупреждение о необходимости использовать [#pragma comment (exestr, "string")](../../preprocessor/comment-c-cpp.md) директивы. Тем не менее это требование является устаревшей и будет изменена в будущем выпуске компилятора. Если вы используете `#pragma` директив, инструмент-компоновщик (LINK.exe) пропускает запись комментария, созданную директивой и выдает предупреждение [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Вместо `#ident` директив, мы рекомендуем использовать строку ресурса версии файла в приложении.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалить `#ident "` *строка* `"` директивы.  
  
## <a name="see-also"></a>См. также  
 [комментарий (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [Предупреждение средств компоновщика LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Работа с файлами ресурсов](../../windows/working-with-resource-files.md)