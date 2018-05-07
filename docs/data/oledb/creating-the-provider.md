---
title: Создание поставщика | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, creating
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b08d2a2f68d174ae7c92d1d6bc0fa2bbb764fdca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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