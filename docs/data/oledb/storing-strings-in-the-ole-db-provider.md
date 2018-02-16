---
title: "Хранение строк в поставщике OLE DB | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 523193d7fa5f18d3d0956d39ca68cdc5d34131b0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Хранение строк в поставщике OLE DB
(MyProviderRS.h), мастер поставщика ATL OLE DB создает пользовательскую запись вызывается `CWindowsFile`. Для обработки двух строк, измените `CWindowsFile` или добавьте собственную запись пользователя, как показано в следующем коде:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 Члены данных `szCommand` и `szText` представляют две строки с `szCommand2` и `szText2` предоставление дополнительных столбцов, при необходимости. Элемент данных `dwBookmark` не требуется для этого простого поставщика только для чтения, но используется позже, чтобы добавить `IRowsetLocate` интерфейса см. в разделе [Усовершенствование простого чтения только поставщика](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==` Оператор сравнивает экземпляров (реализации этого оператора необязателен).  
  
 Если это сделано, поставщик должен быть готов для компиляции и запуска. Чтобы протестировать поставщика, необходимо получатель с соответствующими функциями. [Реализация простых объектов получателей](../../data/oledb/implementing-a-simple-consumer.md) показано создание объекта-получателя для тестирования. Запустите тестовый объект-получатель с поставщиком. Убедитесь в том, что тестовый объект-получатель правильную строки от поставщика при нажатии кнопки **запуска** кнопку в **тестовый объект-получатель** диалоговое окно.  
  
 После успешного тестирования поставщика можно расширить его функциональные возможности, реализовав дополнительные интерфейсы. В примере показано [Усовершенствование простого поставщика только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
## <a name="see-also"></a>См. также  
 [Реализация простого поставщика, предназначенного только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md)