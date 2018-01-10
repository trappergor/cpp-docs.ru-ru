---
title: "Использование нескольких результирующих наборов одной хранимой процедуры | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec887f01e377ffa6295086bbeeb56dcd884d6276
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Использование нескольких результирующих наборов одной хранимой процедуры
Большинство хранимых процедур возвращают несколько результирующих наборов. Хранимые процедуры обычно включают одну или несколько инструкций select. Потребитель должен учитывать для обработки всех результирующих наборов.  
  
### <a name="to-handle-multiple-result-sets"></a>Обработка нескольких результирующих наборов  
  
1.  Создание `CCommand` класса `CMultipleResults` в качестве аргумента шаблона и методом доступа по своему усмотрению. Как правило это динамический или ручной метод доступа. Если вы используете другой тип метода доступа, не можно определить выходных столбцов для каждого набора строк.  
  
2.  Выполните хранимую процедуру в обычном режиме и привяжите столбцы (в разделе [инструкции по выполнению выборки данных?](../../data/oledb/fetching-data.md)).  
  
3.  Используйте данные.  
  
4.  Вызовите `GetNextResult` на `CCommand` класса. Если доступен другой результирующий набор строк, `GetNextResult` возвращает значение S_OK и вы связывание столбцов при использовании метода доступа вручную. Если `GetNextResult` возвращает сообщение об ошибке существует результирующих наборов больше нет доступных.  
  
## <a name="see-also"></a>См. также  
 [Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)