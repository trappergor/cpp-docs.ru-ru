---
title: "Предупреждение (уровень 4) C4985 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4985
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4a36692420ea9d5547f236c1e5dfeaa269afbb67
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4985"></a>Предупреждение компилятора (уровень 4) C4985
"имя символа": атрибуты отсутствуют в предыдущем объявлении.  
  
 Примечания SAL к текущему объявлению или определению метода отличаются от примечаний к предыдущему объявлению. В определении и объявлениях метода должны использоваться одинаковые примечания SAL.  
  
 Язык примечаний к исходному коду (SAL), созданный Майкрософт, предоставляет набор примечаний, описывающих способы использования функцией ее параметров, предположения функции о ее параметрах и гарантии, которые она дает по окончании. Примечания определены в файле заголовка sal.h.  
  
 Обратите внимание, что макросы SAL не будут расширяться, если в проекте не [/ analyze](../../build/reference/analyze-code-analysis.md) указанный флаг. При указании **/analyze**компилятор может выдать ошибку C4985, даже если без **/analyze**не было никаких ошибок или предупреждений.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  В определении метода и всех его объявлениях следует использовать одинаковые примечания SAL.  
  
## <a name="see-also"></a>См. также  
 [Заметки SAL](../../c-runtime-library/sal-annotations.md)
