---
title: "Проверка на наличие ошибок извлечения | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 05e2c94cc23a7ad75edcd92721de538ac008d65b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="testing-for-extraction-errors"></a>Проверка на наличие ошибок извлечения
Функции обработки ошибок вывода, рассматриваемые в разделе [Функции обработки ошибок](../standard-library/output-file-stream-member-functions.md), применяются к входным потокам. Проверка на наличие ошибок во время извлечения очень важна. Представьте себе следующую ситуацию:  
  
```  
cin>> n;  
```  
  
 Если `n` — это целое число со знаком, значение больше 32 767 (максимальное допустимое значение или MAX_INT) задает бит `fail` потока, а объект `cin` становится непригодным для использования. Все последующие извлечения приводят к немедленному возврату без сохранения значений.  
  
## <a name="see-also"></a>См. также  
 [Потоки ввода](../standard-library/input-streams.md)


