---
title: "Дата и время: поддержка SYSTEMTIME | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "системное время"
  - "Структура FILETIME, класс CTime"
  - "Форматирование времени [C++]"
  - "SYSTEMTIME - структура"
  - "даты [C++] MFC"
  - "форматирование [C++], время"
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Дата и время: поддержка SYSTEMTIME
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

 [CTime](../Topic/CTime%20Class.md) имеет конструкторы, которые принимают время системы и файлов из Win32. Если вы используете в этих целях объекты `CTime`, вам следует соответствующим образом изменить их инициализацию, следуя указаниям из данной статьи.  
  
 Сведения о структуре SYSTEMTIME см. в разделе [SYSTEMTIME](../mfc/reference/systemtime-structure1.md). Сведения о структуре FILETIME см. в разделе [FILETIME](../mfc/reference/filetime-structure.md).  
  
 MFC все еще предоставляет конструкторы `CTime`, которые принимают аргументы в стиле MS-DOS, но, начиная с MFC версии 3.0, класс `CTime` также поддерживает конструктор, который принимает структуру `SYSTEMTIME` Win32, и другой конструктор, который принимает структуру `FILETIME` Win32.  
  
 Новые конструкторы `CTime`:  
  
-   CTime (const SYSTEMTIME & `sysTime`);  
  
-   CTime (const FILETIME & `fileTime`);  
  
 Параметр `fileTime` является ссылкой на структуру `FILETIME` Win32, которая представляет время в виде 64-разрядного значения, так как этот формат более удобен для внутренней памяти, чем структура `SYSTEMTIME` и формат, использовавшийся Win32 для представления времени создания файла.  
  
 Если ваш код содержит объект `CTime`, инициализированный с системным временем, вам следует использовать конструктор `SYSTEMTIME` в Win32.  
  
 Скорее всего, вы не будете использовать `CTime` `FILETIME` инициализации напрямую. Если вы используете `CFile` объекта для работы с файлом [CFile::GetStatus](../mfc/reference/cfile-class.md#getstatus) получает метку времени файла через `CTime` объект инициализирован с `FILETIME` структуры.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Общие программирования даты и времени в MFC](../atl-mfc-shared/date-and-time.md)  
  
-   [Поддержка автоматизации при программировании даты и времени](../Topic/Date%20and%20Time:%20Automation%20Support.md)  
  
-   [Классы общего назначения для программирования даты и времени](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>См. также раздел  
 [Дата и время](../atl-mfc-shared/date-and-time.md)

