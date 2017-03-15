---
title: "Классы DAO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], классы"
  - "классы баз данных [C++], DAO"
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Классы DAO
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти классы работают с другими классами платформы приложения для удобного доступа к базам данных \(DAO\) объекта доступа к данным, которые используют одно и то же ядра СУБД как Microsoft Visual Basic и Microsoft Access.  Классы DAO можно также получить множество различных баз данных, для которых драйверы ODBC \(ODBC\).  
  
 Программ, использующих базы данных DAO имеют по крайней мере объект `CDaoDatabase` и объект `CDaoRecordset`.  
  
> [!NOTE]
>  Что касается Visual C\+\+ .NET, то среда и мастера Visual C\+\+ больше не поддерживают DAO \(хотя классы DAO включены и вы по\-прежнему можете их использовать\).  Майкрософт рекомендует использовать ODBC для новых проектов MFC.  DAO необходимо использовать только для поддержки существующих приложений.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Управление именованный, защищенный паролем сеанс базы данных из входа, чтобы выход из системы.  Большинство программ используют рабочую область по умолчанию.  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 Подключение к базе данных через, можно работает на данные.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 Представляет набор записей, выбранных из источника данных.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Представление, которое отображает записи базы данных в элементах управления.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Представляет определение запроса, как правило, сохраненное в базе данных.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 Представляет хранимое определение базовой или подключенной таблицы.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Представляет условие исключения, поступающие от классов DAO.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 Поддерживает процедуры обмена полями записей \(DAO DFX\), используемые классами баз данных DAO.  Обычно непосредственно не будет использовать этот класс.  
  
## Связанные классы  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Инкапсулирует дескриптор хранилище для большого двоичного объекта \(BLOB\), например растровое изображение.  объекты `CLongBinary` используются для управления большими объектами данных, хранящихся в таблицах базы данных.  
  
 [COleCurrency](../Topic/COleCurrency%20Class.md)  
 Программа\-оболочка для типа **CURRENCY** ole\-автоматизации, с фиксированной запятой арифметического типа, с 15 цифрами перед десятичной запятой и 4 цифр позже.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Программа\-оболочка для типа **date** ole\-автоматизации.  Представляет значения даты и времени.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Программа\-оболочка для типа **VARIANT** ole\-автоматизации.  Данные в **VARIANT**, можно хранить в несколько форматов.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)