---
title: Источники данных и сеансы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d93f6aba8e9fad27054c731d37e6df28b54eacda
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="data-sources-and-sessions"></a>Источники данных и сеансы
На следующем рисунке показана классы, поддерживающие подключение и доступ к источнику данных. Каждый класс основан на реализации стандартного компонента OLE DB.  
  
 ![Данные источника и классы сеансов](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")  
Классы источника данных и сеанса  
  
 Ниже приведены классы:  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md) этот класс создает объект источника данных, который создает и управляет подключением к источнику данных через поставщик OLE DB. Источник данных принимает сведения, такие как сведения источника данных адреса и проверки подлинности в виде строки подключения.  
  
     Также стоит отметить, что вспомогательный класс [CEnumerator](../../data/oledb/cenumerator-class.md) часто используется перед все подключения, чтобы получить список поставщиков, зарегистрированных в системе. Это позволяет выбрать поставщика в качестве источника данных. Например **свойства связи данных** диалоговое окно использует этот класс для заполнения списка поставщиков на **поставщики** вкладки. Это эквивалентно **SQLBrowseConnect** или **SQLDriverConnect** функции.  
  
-   [CSession](../../data/oledb/csession-class.md) этот класс создает экземпляр объекта сеанса, который представляет собой сеанс единого доступа к источнику данных. Тем не менее можно создать несколько сеансов на источнике данных. Для каждого сеанса можно создать наборы строк, команд и других объектов для доступа к данным из источника данных. Сеанс обрабатывает транзакции.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)