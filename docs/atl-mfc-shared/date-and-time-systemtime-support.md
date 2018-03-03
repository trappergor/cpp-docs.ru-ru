---
title: "Дата и время: поддержка SYSTEMTIME | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 405c245cdab6426330915c945cd77f8336e68c9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="date-and-time-systemtime-support"></a>Дата и время: поддержка SYSTEMTIME
[CTime](../atl-mfc-shared/reference/ctime-class.md) класс содержит конструкторы, которые принимают время системы и файлов из Win32. Если вы используете в этих целях объекты `CTime`, вам следует соответствующим образом изменить их инициализацию, следуя указаниям из данной статьи.  
  
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
  
-   [Поддержка автоматизации программирования даты и времени](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [Классы общего назначения для программирования даты и времени](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>См. также  
 [Дата и время](../atl-mfc-shared/date-and-time.md)

