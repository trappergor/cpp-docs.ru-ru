---
title: "Подключение к Oracle | Microsoft Docs"
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
  - "подключения [C++], базы данных"
  - "подключения к базе данных [C++], Oracle"
  - "базы данных [C++], подключение к"
  - "Oracle [C++], создание подключений"
  - "базы данных Oracle [C++]"
  - "базы данных Oracle [C++], подключения"
ms.assetid: d317e763-44aa-47c9-abe8-261d513d894f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Подключение к Oracle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для настройки подключения к Oracle ODBC DSN или OLE DB необходимо установить клиентские компоненты Oracle SQL\*Net.  SQL\*Net — это транспортный уровень сети Oracle.  Большинство драйверов Oracle ODBC, включая драйвер Майкрософт и схему поставщика Microsoft OLE DB Oracle, обращаются напрямую к этому уровню SQL\*Net.  
  
 После настройки SQL\*Net обратите внимание на строку подключения SQL\*Net.  Обычно она состоит из спецификатора для имени сервера базы данных Oracle и типа Интернет\-протокола \(например, TCP\/IP и именованные каналы\).  Нередко строка подключения SQL\*Net сопоставляется псевдониму.  В этом случае нужно запомнить только псевдоним.  За дополнительными сведениями о настройке SQL\*Net обращайтесь к администратору Oracle, см. документацию SQL\*Net либо файл справки для драйвера Oracle ODBC \(там можно найти примеры строк подключения\).  
  
## См. также  
 [Создание подключений к базе данных](../Topic/Creating%20Database%20Connections.md)