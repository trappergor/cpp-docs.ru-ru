---
title: "Распространение компонентов ODBC среди клиентов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "компоненты [C++]"
  - "компоненты [C++], распространение"
  - "компоненты [C++], повторное распространение"
  - "Администратор ODBC"
  - "компоненты ODBC, повторное распространение"
  - "ODBC, распространение компонентов"
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Распространение компонентов ODBC среди клиентов
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При встраивании программ администратора ODBC в приложение необходимо также передать пользователям файлы, которые запускают данные программы.  Эти файлы ODBC находятся в каталоге \\OS\\System компакт\-диска с Visual C\+\+.  Файл Redistrb.wri и лицензионное соглашение в этом каталоге содержат список файлов ODBC, которые можно распространять.  
  
 Обратитесь к документации по всем драйверам ODBC, которые планируется поставлять.  Необходимо определить, какие поставлять библиотеки DLL и другие файлы.  
  
 Также следует ознакомиться с разделом [Настройка поддержки баз данных](../../data/installing-database-support-mfc-atl.md) для получения сведений о компонентах и драйверах ODBC и разделом [Распространение элементов управления](../Topic/Redistributing%20Controls.md), в котором описаны способы распространения элементов управления ActiveX.  
  
 В большинстве случаев понадобится включить еще один файл.  Файл Odbccr32.dll является библиотекой курсоров ODBC.  Данная библиотека предоставляет драйверам первого уровня возможность прямой и обратной прокрутки.  Она также предоставляет возможность поддержки "моментальных снимков".  Дополнительные сведения о библиотеке курсоров ODBC см. в разделе [ODBC. Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md).  
  
 В следующих разделах приводятся дополнительные сведения об использовании ODBC с классами баз данных:  
  
-   [ODBC. Библиотека курсоров ODBC](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC. Настройка источника данных ODBC](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC. Прямой вызов функций ODBC API](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## См. также  
 [Основы ODBC](../../data/odbc/odbc-basics.md)   
 [Администратор ODBC](../../data/odbc/odbc-administrator.md)