---
title: "Создание поставщика OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd59e8e9456cac830e6e86faf404c76816e45349
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="creating-an-ole-db-provider"></a>Создание поставщика OLE DB
Рекомендуемый способ создания поставщика OLE DB является использование мастеров для создания проекта ATL COM и поставщика, а затем измените файлы с помощью шаблонов OLE DB. При настройке поставщика, можно закомментировать нежелательные свойства и добавить дополнительные интерфейсы.  
  
 Порядок действий таков:  
  
1.  Использовать мастер проектов ATL для создания файлы базового проекта и мастер ATL OLE DB Provider для создания поставщика (выберите **поставщика ATL OLE DB** из папки Visual C++ в **добавить класс**).  
  
2.  Измените код в `Execute` метод в CMyProviderRS.h. Пример см. в разделе [чтение строк в поставщик OLE DB](../../data/oledb/reading-strings-into-the-ole-db-provider.md).  
  
3.  Изменение сопоставления свойств в MyProviderDS.h, MyProviderSess.h и MyProviderRS.h. Мастер создает карты свойств, содержащие все свойства, которые может реализовать поставщик. Пройти сопоставления свойств и удалите или закомментируйте свойства, которые поставщик должен поддерживать.  
  
4.  Обновите PROVIDER_COLUMN_MAP, которую можно найти (MyProviderRS.h). Пример см. в разделе [хранения строк в поставщик OLE DB](../../data/oledb/storing-strings-in-the-ole-db-provider.md).  
  
5.  Когда будете готовы для проверки поставщика, его можно проверить, пытаясь найти поставщика в перечислении поставщиков. Примеры кода теста, поиск поставщика в перечислении см [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046) и [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) образцы или только в примере в [реализация простых объектов получателей](../../data/oledb/implementing-a-simple-consumer.md).  
  
6.  Добавьте дополнительные необходимые интерфейсы. Пример см. в разделе [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
    > [!NOTE]
    >  По умолчанию мастер создает код, который OLE DB уровня 0 соответствует. Чтобы убедиться, что приложение остается совместимым с уровнем 0, не удаляйте любой из этих интерфейсов, создаваемые мастером из кода.  
  
## <a name="see-also"></a>См. также  
 [CATDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046)   
 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)