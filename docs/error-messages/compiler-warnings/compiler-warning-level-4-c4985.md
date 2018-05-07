---
title: Предупреждение (уровень 4) C4985 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8f0b62a72d61ee061fd996f93638acba9e7ebb0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4985"></a>Предупреждение компилятора (уровень 4) C4985
"имя символа": атрибуты отсутствуют в предыдущем объявлении.  
  
 Примечания SAL к текущему объявлению или определению метода отличаются от примечаний к предыдущему объявлению. В определении и объявлениях метода должны использоваться одинаковые примечания SAL.  
  
 Язык примечаний к исходному коду (SAL), созданный Майкрософт, предоставляет набор примечаний, описывающих способы использования функцией ее параметров, предположения функции о ее параметрах и гарантии, которые она дает по окончании. Примечания определены в файле заголовка sal.h.  
  
 Обратите внимание на то, что макросы SAL не будут расширяться, если в проекте не указан флаг [/analyze](../../build/reference/analyze-code-analysis.md) . При указании **/analyze**компилятор может выдать ошибку C4985, даже если без **/analyze**не было никаких ошибок или предупреждений.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  В определении метода и всех его объявлениях следует использовать одинаковые примечания SAL.  
  
## <a name="see-also"></a>См. также  
 [Заметки SAL](../../c-runtime-library/sal-annotations.md)