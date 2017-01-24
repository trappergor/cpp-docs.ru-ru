---
title: "Распространение файлов поддержки базы данных | Microsoft Docs"
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
  - "файлы поддержки базы данных [C++], повторное распространение"
  - "распространение файлов поддержки базы данных"
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Распространение файлов поддержки базы данных
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно повторно распространить файлы поддержки для объектов доступа к данным \(DAO\) и технологиям баз данных в пакете Microsoft Data Access SDK.  
  
## Установка файлов поддержки DAO  
 Чтобы получить последнюю версию DAO см. в разделе [Статья 239114: Получение последний пакет обновления для ядра СУБД Microsoft Jet 4.0](http://go.microsoft.com/fwlink/?LinkId=198014) на веб\-сайте поддержки Майкрософт.  
  
## Установка файлов поддержки для пакета Microsoft Data Access SDK  
 Для установки файлов поддержки для ODBC, OLE DB, ActiveX Data Objects \(ADO\) и Remote Data Services \(RDS\) используется Mdac\_typ.exe.  Файл Mdac\_typ.exe расположен в папке. папка \\WCU\\MDAC28\\ на установочном носителе Visual Studio.  Загрузить файл Mdac\_typ.exe можно [Центр загрузки Майкрософт](http://go.microsoft.com/fwlink/?LinkId=198015).  
  
 Дополнительные сведения см. на веб\-сайте [MSDN](http://go.microsoft.com/fwlink/?LinkId=198016), поиск «распространения MDAC 2.8 SP1».  Если для развертывания приложения используются проекты установки Visual Studio, см. раздел [Deployment and Dependencies](http://msdn.microsoft.com/ru-ru/49e9b84d-bd6a-4388-b9ac-46ea79cf0733).  
  
## См. также  
 [Распространение файлов Visual C\+\+](../Topic/Redistributing%20Visual%20C++%20Files.md)