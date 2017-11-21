---
title: "Распространение компонентов ODBC среди клиентов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 861eceef234b77b96179c51979cb7d1c0d09eeeb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="redistributing-odbc-components-to-your-customers"></a>Распространение компонентов ODBC среди клиентов
Если включить возможности программ администратора ODBC в приложение, необходимо также распространить пользователям файлы, запускать эти программы. Эти файлы ODBC находятся в каталоге \OS\System на компакт-диске Visual C++. Файл Redistrb.wri и лицензионное соглашение, в том же каталоге содержат список файлов ODBC, которые можно распространить повторно.  
  
 Обратитесь к документации по всем драйверам ODBC, которые вы собираетесь отправить. Необходимо определить, какие библиотеки DLL и другие файлы для отправки. Также следует ознакомиться с [распространение компонентов ODBC среди клиентов](../../data/odbc/redistributing-odbc-components-to-your-customers.md), который объясняет распространение компонентов ODBC.  
  
 Кроме того необходимо включить еще один файл, в большинстве случаев. Odbccr32.dll является библиотека курсоров ODBC. Эта библиотека предоставляет драйверам первого уровня возможность прямой и обратной прокрутки. Он также предоставляет возможность поддержки моментальных снимков. Дополнительные сведения о библиотеке курсоров ODBC см. в разделе [ODBC: библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
 Дополнительные сведения об использовании ODBC с классами баз данных в следующих разделах.  
  
-   [ODBC. Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC. Настройка источника данных ODBC](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC. Прямой вызов функций API ODBC](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## <a name="see-also"></a>См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)   
 [Администратор ODBC](../../data/odbc/odbc-administrator.md)