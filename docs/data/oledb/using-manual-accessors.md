---
title: Использование методов ручного доступа | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8805878f880d1c195ddf89abc283719e73ff5182
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808931"
---
# <a name="using-manual-accessors"></a>Использование методов ручного доступа

Существует четыре какие действия можно выполнить при обработке Неизвестная команда:  
  
- Определение параметров  
  
- Выполните команду  
  
- Определить выходные столбцы.  
  
- Проверить, есть несколько наборов строк, возвращаемого значения  
  
Чтобы выполнить эти действия с Шаблоны потребителей OLE DB, используйте `CManualAccessor` класса и выполните следующие действия:  
  
1. Откройте `CCommand` со `CManualAccessor` как параметр шаблона.  
  
    ```cpp  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
1. Запрос сеанса для `IDBSchemaRowset` интерфейса и использовать набор строк параметров процедуры. Если `IDBSchemaRowset` интерфейс недоступен, запрашивать `ICommandWithParameters` интерфейс. Вызовите `GetParameterInfo` сведения. Если ни один из интерфейсов, можно предположить, что параметры отсутствуют.  
  
1. Для каждого параметра вызова `AddParameterEntry` добавить параметры и установить их.  
  
1. Открыть набор строк, но задать для параметра привязки **false**.  
  
1. Вызовите `GetColumnInfo` для получения выходных столбцов. Используйте `AddBindEntry` добавляемый привязки выходного столбца.  
  
1. Вызовите `GetNextResult` для определения того, если доступны дополнительные наборы строк. Повторите шаги 2 – 5.  
  
Пример метода доступа вручную, см. в разделе `CDBListView::CallProcedure` в [DBVIEWER](https://github.com/Microsoft/VCSamples) образца.  
  
## <a name="see-also"></a>См. также  

[Использование методов доступа](../../data/oledb/using-accessors.md)