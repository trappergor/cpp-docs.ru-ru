---
title: Использование нескольких результирующих наборов одной хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 70fab2751e216ca90dbe09e31c88f9aa80aa7b90
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808268"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Использование нескольких результирующих наборов одной хранимой процедуры

Большинство хранимых процедур возвращают несколько результирующих наборов. Хранимая процедура обычно включает в себя один или несколько инструкций select. Потребитель должен учитывать это включение для обработки всех результирующих наборов.  
  
## <a name="to-handle-multiple-result-sets"></a>Обработка нескольких результирующих наборов  
  
1. Создание `CCommand` класса `CMultipleResults` как аргумент шаблона и методом доступа по своему усмотрению, обычно метод доступа динамический или вручную. Если вы используете другой тип метода доступа, может не появиться возможность определить выходные столбцы для каждого набора строк.  
  
1. Выполните хранимую процедуру как обычно и привяжите столбцы (см. в разделе [инструкции выборки данных?](../../data/oledb/fetching-data.md)).  
  
1. Используйте данные.  
  
1. Вызовите `GetNextResult` на `CCommand` класса. Если доступен другой результирующий набор строк, `GetNextResult` возвращает S_OK, и вы связывание столбцов при использовании метода доступа вручную. Если `GetNextResult` возвращает ошибку, существуют результирующих наборов больше нет доступных.  
  
## <a name="see-also"></a>См. также  

[Использование хранимых процедур](../../data/oledb/using-stored-procedures.md)