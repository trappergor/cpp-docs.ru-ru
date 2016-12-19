---
title: "ODBC и MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "подключения [C++], источник данных"
  - "подключения [C++], базы данных"
  - "источники данных [C++], подключение к"
  - "подключения к базе данных [C++], Классы MFC ODBC"
  - "базы данных [C++], подключение к"
  - "MFC [C++], ODBC и"
  - "ODBC [C++], MFC - библиотека"
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC и MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Для использования классов баз данных MFC для создания приложений, предназначенных для платформы Win32 \(таких как Windows NT\), необходимо иметь соответствующий драйвер ODBC для источника данных.  Некоторые драйверы входят в поставку Visual C\+\+; какие\-то драйверы можно приобрести у Майкрософт и других производителей.  Дополнительные сведения см. в разделе [Список драйверов ODBC](../../data/odbc/odbc-driver-list.md).  
  
 В этом разделе представлены основные понятия классов баз данных на основе ODBC библиотеки Microsoft Foundation Classes \(MFC\) и общие сведения о взаимодействии классов.  Дополнительные сведения об ODBC и MFC см. в следующих разделах:  
  
-   [Подключение к источнику данных](../../data/odbc/connecting-to-a-data-source.md)  
  
-   [Выбор записей и работа с ними](../../data/odbc/selecting-and-manipulating-records.md)  
  
-   [Отображение и обработка данных в форме](../Topic/Displaying%20and%20Manipulating%20Data%20in%20a%20Form.md)  
  
-   [Работа с документами и представлениями](../../data/odbc/working-with-documents-and-views.md)  
  
-   [Доступ к ODBC и SQL](../../data/odbc/access-to-odbc-and-sql.md)  
  
-   [Дополнительные сведения о классах ODBC MFC](../../data/odbc/further-reading-about-the-mfc-odbc-classes.md)  
  
 Классы баз данных MFC на основе ODBC предназначены для предоставления доступа ко всем базам данных, для которых доступны драйверы ODBC.  Поскольку классы используют ODBC, приложение может осуществлять доступ к данным во многих форматах и различных локальных\/удаленных конфигурациях.  Не требуется писать специальные коды для обработки различных систем управления базами данных \(DBMS\).  Если у пользователей есть соответствующий драйвер ODBC для данных, к которым они хотят получить доступ, они могут использовать программу для выполнения операций с данными, хранящимися в таблицах.  
  
## См. также  
 [Интерфейс ODBC \(ODBC\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)