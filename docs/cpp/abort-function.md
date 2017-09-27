---
title: "Функция Abort | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Abort
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 169c76f4925dd02aeffbaa510526ce3caa53e93f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="abort-function"></a>Функция abort
**Прервать** функции, также объявляется в стандартном включаемом файле STDLIB. H, завершает программу C++. Разница между **выйти из** и **прервать** является то, что **выхода** происходит обработка завершения среды выполнения C++ (глобальных объектов, будут вызваны деструкторы), в то время как **прервать** программа завершается сразу. Дополнительные сведения см. в разделе [прервать](../c-runtime-library/reference/abort.md) в *Справочник по библиотеке времени выполнения*.  
  
## <a name="see-also"></a>См. также  
 [Завершение программы](../cpp/program-termination.md)
