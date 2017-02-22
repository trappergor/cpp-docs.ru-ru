---
title: "Установка поддержки баз данных MFC | Microsoft Docs"
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
  - "DAO [C++], установка компонентов"
  - "базы данных [C++], установка компонентов поддержки баз данных"
  - "базы данных [C++], MFC - библиотека"
  - "установка DAO"
  - "установка ODBC"
  - "компоненты ODBC [C++], установка"
  - "драйверы ODBC [C++], установка"
ms.assetid: a6c2fc84-9e0e-4f39-a464-0bcbc415b946
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Установка поддержки баз данных MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

##  <a name="_core_odbc_drivers_installed"></a> Установка драйверов ODBC  
 Программа установки устанавливает следующие драйверы ODBC:  
  
-   Драйвер Microsoft Access  
  
-   Драйвер Microsoft dBASE  
  
-   Драйвер Microsoft Excel  
  
-   Драйвер Microsoft FoxPro VFP  
  
-   Драйвер Microsoft Visual FoxPro  
  
-   Драйвер Microsoft ODBC для Oracle  
  
-   Драйвер Microsoft Paradox  
  
-   Драйвер Microsoft Text  
  
-   Драйвер Microsoft SQL Server  
  
 Сведения о приобретении дополнительных драйверов и список драйверов ODBC, поставляемых с данной версией Visual C\+\+, см. в разделе [Список драйверов ODBC](../data/odbc/odbc-driver-list.md).  
  
##  <a name="_core_odbc_sdk_components_installed"></a> Установка компонентов ODBC SDK  
 Visual C\+\+ содержит основные компоненты ODBC, в число которых входят необходимые файлы заголовков, библиотеки, библиотеки DLL и средства разработки.  В средства разработки входит приложение "Панель администратора ODBC", которое используется для настройки источников данных ODBC, и диспетчер драйвера ODBC.  В состав также входят драйверы ODBC для большинства распространенных СУБД, указанных в списке [Устанавливаемые драйверы ODBC](#_core_odbc_drivers_installed).  
  
 ODBC SDK предоставляет дополнительные сведения и инструментальные средства для написания и тестирования драйверов ODBC.  Обратите внимание, что теперь ODBC SDK не входит в установочный носитель Visual C\+\+ .NET и доступен как часть [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)], который устанавливается с диска "Подготовка системы для Visual Studio .NET".  
  
##  <a name="_core_dao_sdk_components_installed"></a> Установка компонентов DAO SDK  
  
> [!NOTE]
>  Майкрософт рекомендует для новых проектов использовать OLE DB или ODBC.  DAO следует использовать только для обслуживания существующих приложений.  
  
 Следующие компоненты DAO SDK устанавливаются по умолчанию:  
  
-   Microsoft Jet \(4.0 SP3\)  
  
-   Microsoft Jet \(3.x MDB\)  
  
-   Microsoft Jet \(1.x, 2.x\)  
  
-   Все форматы баз данных перечислены в разделе [Базы данных, к которым можно получить доступ с помощью интерфейсов DAO и ODBC](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md).  
  
 В Visual C\+\+ .NET DAO SDK устанавливается с диска "Подготовка системы для Visual Studio .NET".  Запустите исполняемый файл из каталога \\Jet\\Jetsetup.exe.  
  
> [!NOTE]
>  Microsoft рекомендует использовать Jet 4.0 с пакетом обновления 3 \(версия 2927.04\) или более поздней версии.  Jet 4.0 с пакетом обновления 3 поставляется с Windows 2000 и Windows ME.  Использование ядра Jet указанной версии позволяет уменьшить число версий Jet, которые необходимо протестировать на совместимость с приложением.  Windows XP может поставляться с другой версией ядра Jet.  См. "Замечания о распространении компонентов DAO" в разделе [Распространение элементов управления](../Topic/Redistributing%20Controls.md).  
  
 Если необходимо установить другие компоненты DAO SDK, например, классы C\+\+ DAO SDK, файлы примеров или файлы справки DAO, установите DAO SDK с компакт\-диска Visual C\+\+ 6.0.  
  
 Для обновлений и новостей о OLE DB см. на веб\-сайте универсального доступа к данным в [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548).  
  
## См. также  
 [Программирование доступа к данным \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)