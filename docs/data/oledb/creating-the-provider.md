---
title: "Создание поставщика | Документы Microsoft"
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
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5521215560c84c19f7b661f0c9662752374b68e4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="creating-the-provider"></a>Создание поставщика
#### <a name="to-create-an-ole-db-provider-with-the-atl-ole-db-provider-wizard"></a>Создание поставщика OLE DB с помощью мастера поставщика ATL OLE DB  
  
1.  Щелкните правой кнопкой мыши проект.  
  
2.  В контекстном меню выберите **добавить**, а затем нажмите кнопку **Добавление класса**.  
  
3.  В **добавить класс** выберите **поставщика ATL OLE DB** значок, а затем щелкните **откройте**.  
  
4.  В мастере поставщиков OLE DB ATL введите короткое имя поставщика в **короткое имя** поле. В последующих разделах используется короткое имя «MyProvider», но можно использовать другое имя. Остальные поля заполняются в соответствии с введенное имя.  
  
5.  При необходимости измените имя поля. Помимо имен объектов и файлов можно изменять следующие параметры:  
  
    -   **Компонентный класс**: имя, которое COM использует для создания поставщика.  
  
    -   **Идентификатор progID**: программный идентификатор, который представляет собой текстовую строку, которая может использоваться вместо GUID.  
  
    -   **Версия**: используется совместно с ProgID и coclass для создания программного идентификатора, зависящие от версии.  
  
6.  Нажмите кнопку **Готово**.  
  
## <a name="see-also"></a>См. также  
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)