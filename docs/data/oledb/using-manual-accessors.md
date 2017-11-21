---
title: "Использование методов ручного доступа | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3a37f721c372f3ad11000aec023ef74fb1fb1097
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="using-manual-accessors"></a>Использование методов ручного доступа
Существует четыре задач при обработке неизвестной команды:  
  
-   Определить параметры  
  
-   Выполните команду  
  
-   Определить выходные столбцы.  
  
-   Если есть несколько наборов строк, возвращаемых  
  
 Чтобы сделать это с помощью шаблонов потребителей OLE DB, используйте `CManualAccessor` класса и выполните следующие действия:  
  
1.  Откройте `CCommand` объекта с `CManualAccessor` как параметр шаблона.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Запросите сеанс для **IDBSchemaRowset** интерфейса и используйте набор строк параметров процедуры. Если **IDBSchemaRowset** интерфейс недоступен, запросить `ICommandWithParameters` интерфейса. Вызовите `GetParameterInfo` сведения. Если ни один из интерфейсов, можно предположить, что нет параметров.  
  
3.  Для каждого параметра вызова `AddParameterEntry` добавить параметры и установить их.  
  
4.  Открыть набор строк, но задать для параметра bind **false**.  
  
5.  Вызовите `GetColumnInfo` для получения выходных столбцов. Используйте `AddBindEntry` Добавление привязки выходного столбца.  
  
6.  Вызовите `GetNextResult` для определения того, если доступны дополнительные наборы строк. Повторите шаги 2 – 5.  
  
 Пример метода доступа вручную см. в разделе **CDBListView::CallProcedure** в [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) образца.  
  
## <a name="see-also"></a>См. также  
 [Использование методов доступа](../../data/oledb/using-accessors.md)