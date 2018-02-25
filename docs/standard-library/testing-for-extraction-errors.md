---
title: "Проверка на наличие ошибок извлечения | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 232dbd4312bbb8a0f16b6095622680f070ff2905
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="testing-for-extraction-errors"></a>Проверка на наличие ошибок извлечения
Функции обработки ошибок вывода, рассматриваемые в разделе [Функции обработки ошибок](../standard-library/output-file-stream-member-functions.md), применяются к входным потокам. Проверка на наличие ошибок во время извлечения очень важна. Представьте себе следующую ситуацию:  
  
```  
cin>> n;  
```  
  
 Если `n` — это целое число со знаком, значение больше 32 767 (максимальное допустимое значение или MAX_INT) задает бит `fail` потока, а объект `cin` становится непригодным для использования. Все последующие извлечения приводят к немедленному возврату без сохранения значений.  
  
## <a name="see-also"></a>См. также  
 [Потоки ввода](../standard-library/input-streams.md)

