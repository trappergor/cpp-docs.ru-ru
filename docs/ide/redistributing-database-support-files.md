---
title: Распространение файлов поддержки базы данных | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- redistributing database support files
- database support files [C++], redistributing
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a51697367480569e2d27a4cb67791f5fe4d39a8f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "33323879"
---
# <a name="redistributing-database-support-files"></a>Распространение файлов поддержки базы данных
Вы можете повторно распространять файлы поддержки для интерфейса DAO и технологий баз данных в пакете SDK Майкрософт для доступа к данным.  
  
## <a name="installing-dao-support-files"></a>Установка файлов поддержки DAO  
 Чтобы получить последнюю версию DAO, см. [статью 239114 "Получение последнего пакета обновления для ядра СУБД Microsoft Jet 4.0"](http://go.microsoft.com/fwlink/p/?linkid=198014) на веб-сайте службы поддержки Майкрософт.  
  
## <a name="installing-microsoft-data-access-sdk-support-files"></a>Установка файлов поддержки для пакета SDK Майкрософт для доступа к данным  
 Используйте Mdac_typ.exe, чтобы установить поддержку для ODBC, OLE DB, объектов данных ActiveX (ADO) и Remote Data Services (RDS). Mdac_typ.exe находится в папке ..\WCU\MDAC28\ на установочном носителе Visual Studio. Вы также можете скачать Mdac_typ.exe с веб-сайта [Центр загрузки Майкрософт](http://go.microsoft.com/fwlink/p/?linkid=198015).  
  
 Для получения дополнительных сведений о веб-сайте [MSDN](http://go.microsoft.com/fwlink/p/?linkid=198016) выполните поиск по запросу "Redistributing MDAC 2.8 SP1" (Повторное распространение MDAC 2.8 с пакетом обновления 1 (SP1)). Если вы используете проекты установки Visual Studio для развертывания приложения, см. раздел [Развертывание и зависимости](http://msdn.microsoft.com/en-us/49e9b84d-bd6a-4388-b9ac-46ea79cf0733).  
  
## <a name="see-also"></a>См. также  
 [Распространение файлов Visual C++](../ide/redistributing-visual-cpp-files.md)