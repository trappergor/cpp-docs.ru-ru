---
title: 'Дата и время: поддержка SYSTEMTIME | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a4628d2db9c454bb689d4eb8316b77986588047
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860489"
---
# <a name="date-and-time-systemtime-support"></a>Дата и время: поддержка SYSTEMTIME

[CTime](../atl-mfc-shared/reference/ctime-class.md) класс содержит конструкторы, которые принимают время системы и файлов из Win32. Если вы используете в этих целях объекты `CTime`, вам следует соответствующим образом изменить их инициализацию, следуя указаниям из данной статьи.

Сведения о структуре SYSTEMTIME см. в разделе [SYSTEMTIME](../mfc/reference/systemtime-structure1.md). Сведения о структуре FILETIME см. в разделе [FILETIME](../mfc/reference/filetime-structure.md).

MFC все еще предоставляет конструкторы `CTime`, которые принимают аргументы в стиле MS-DOS, но, начиная с MFC версии 3.0, класс `CTime` также поддерживает конструктор, который принимает структуру `SYSTEMTIME` Win32, и другой конструктор, который принимает структуру `FILETIME` Win32.

Новые конструкторы `CTime`:

- CTime (const SYSTEMTIME & `sysTime`);

- CTime (const FILETIME & `fileTime`);

*FileTime* параметр является ссылкой на Win32 `FILETIME` структуры, который представляет время в виде 64-разрядное значение, более удобный формат для внутренней памяти, чем `SYSTEMTIME` структуру и формат, используемый Win32 для — Это время создания файла.

Если ваш код содержит объект `CTime`, инициализированный с системным временем, вам следует использовать конструктор `SYSTEMTIME` в Win32.

Скорее всего, вы не будете использовать `CTime` `FILETIME` инициализации напрямую. Если вы используете `CFile` объекта для работы с файлом [CFile::GetStatus](../mfc/reference/cfile-class.md#getstatus) получает метку времени файла через `CTime` инициализированный с помощью `FILETIME` структуры.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Общие программирования даты и времени в MFC](../atl-mfc-shared/date-and-time.md)

- [Поддержка модели автоматизации для программирования даты и времени](../atl-mfc-shared/date-and-time-automation-support.md)

## <a name="see-also"></a>См. также

[Дата и время](../atl-mfc-shared/date-and-time.md)
