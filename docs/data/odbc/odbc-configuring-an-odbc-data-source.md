---
title: 'ODBC: Настройка источника данных ODBC | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 93b2158005b7cd31fc6a3710812d54a3968ee014
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089156"
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