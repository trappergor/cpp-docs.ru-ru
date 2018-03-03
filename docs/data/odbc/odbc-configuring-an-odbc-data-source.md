---
title: "ODBC: Настройка источника данных ODBC | Документы Microsoft"
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
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5bf7d2b1708e74d50adb417f531c741a467ed889
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-configuring-an-odbc-data-source"></a>ODBC. Настройка источника данных ODBC
Для использования [источника данных](../../data/odbc/data-source-odbc.md) с помощью приложения, разработанные вами для его настройки необходимо использовать администратор ODBC. Администратор ODBC сохраняет сведения о доступных источников данных и сведения об их подключении в реестре Windows. Используйте администратор ODBC для добавления, изменения и удаления источников данных в **источники данных** диалоговое окно и для добавления и удаления драйверов ODBC.  
  
> [!NOTE]
>  Эти сведения применимы при использовании классов MFC объекта доступа к данным (DAO) для доступа к ODBC и при использовании классов MFC ODBC.  
  
 Администратор ODBC устанавливается автоматически вместе с поддержкой базы данных библиотеки Microsoft Foundation Classes (MFC). Дополнительные сведения о программе администратора ODBC см. в разделе [администратор ODBC](../../data/odbc/odbc-administrator.md) и системой документации ODBC API ссылку справки.  
  
 Сведения о способах написания программ установки и администрирования ODBC для приложений баз данных MFC[см](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md).  
  
## <a name="see-also"></a>См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)   
 [ODBC. Прямой вызов функций API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)