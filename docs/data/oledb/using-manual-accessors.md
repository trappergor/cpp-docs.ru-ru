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
ms.openlocfilehash: 236fd1809fa012262f3a98f0f1856f3bbff6b454
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340868"
---
# <a name="using-manual-accessors"></a>Использование методов ручного доступа
Существует четыре какие действия можно выполнить при обработке Неизвестная команда:  
  
-   Определение параметров  
  
-   Выполните команду  
  
-   Определить выходные столбцы.  
  
-   Проверить, есть несколько наборов строк, возвращаемого значения  
  
 Чтобы сделать это с помощью шаблонов потребителей OLE DB, используйте `CManualAccessor` класса и выполните следующие действия:  
  
1.  Откройте `CCommand` со `CManualAccessor` как параметр шаблона.  
  
    ```cpp  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Запрос сеанса для `IDBSchemaRowset` интерфейса и использовать набор строк параметров процедуры. Если `IDBSchemaRowset` интерфейс недоступен, запрашивать `ICommandWithParameters` интерфейс. Вызовите `GetParameterInfo` сведения. Если ни один из интерфейсов, можно предположить, что параметры отсутствуют.  
  
3.  Для каждого параметра вызова `AddParameterEntry` добавить параметры и установить их.  
  
4.  Открыть набор строк, но задать для параметра привязки **false**.  
  
5.  Вызовите `GetColumnInfo` для получения выходных столбцов. Используйте `AddBindEntry` добавляемый привязки выходного столбца.  
  
6.  Вызовите `GetNextResult` для определения того, если доступны дополнительные наборы строк. Повторите шаги 2 – 5.  
  
 Пример метода доступа вручную, см. в разделе `CDBListView::CallProcedure` в [DBVIEWER](http://msdn.microsoft.com/07620f99-c347-4d09-9ebc-2459e8049832) образца.  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)